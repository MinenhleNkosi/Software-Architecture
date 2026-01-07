# COMPREHENSIVE CODE EXAMPLES

#### Concept: Performance - Asynchronous Programming
#### Level 1 - Basic Example (Understanding)

**Wrong Way (Synchronous - Blocks Thread):**

```cs
// BAD: Synchronous call blocks the thread
public class HotelController : ControllerBase
{
    private readonly HotelService _service;
    
    public HotelController(HotelService service)
    {
        _service = service;
    }
    
    [HttpGet("search")]
    public IActionResult SearchHotels(string destination)
    {
        // This BLOCKS the thread while waiting for database
        // Under load, thread pool exhaustion occurs
        var hotels = _service.GetHotels(destination); // ⚠️ Synchronous!
        return Ok(hotels);
    }
}
```

**Console Output Under Load:**
```
Request 1: Thread 1 - Start
Request 2: Thread 2 - Start
Request 3: Waiting... (no threads available)
Request 4: Waiting...
Request 1: Thread 1 - Complete (3000ms)
Request 3: Thread 1 - Start (reused thread)
```

**Right Way (Asynchronous - Non-Blocking):**

```cs
// GOOD: Async/await releases thread while waiting
public class HotelController : ControllerBase
{
    private readonly HotelService _service;
    
    // Dependency injection (C# 12 primary constructor not used here for clarity)
    public HotelController(HotelService service)
    {
        _service = service;
    }
    
    [HttpGet("search")]
    public async Task<IActionResult> SearchHotelsAsync(string destination)
    {
        // 'await' releases thread back to pool while waiting
        // Thread can handle other requests
        var hotels = await _service.GetHotelsAsync(destination); // Async!
        return Ok(hotels);
    }
}
```

**Console Output Under Load:**
```
Request 1: Thread 1 - Start, await (thread released)
Request 2: Thread 1 - Start, await (same thread reused!)
Request 3: Thread 2 - Start, await
Request 4: Thread 2 - Start, await (same thread reused!)
Request 1: Thread 3 - Resume & Complete (500ms)
Request 2: Thread 3 - Resume & Complete (500ms)
```

**C# 12 Feature Used**: While primary constructors are available, this example uses traditional DI for clarity. In C# 12, you could write:

```cs
public class HotelController(HotelService service) : ControllerBase
{
    [HttpGet("search")]
    public async Task<IActionResult> SearchHotelsAsync(string destination)
    {
        var hotels = await service.GetHotelsAsync(destination);
        return Ok(hotels);
    }
}
```

