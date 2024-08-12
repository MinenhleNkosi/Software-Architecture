# What is software architecture?
Just as an architect designs a building and oversees its construction based on that design, the main goal of a **software architect** is to ensure that the software application is implemented well; and good implementation requires the design of a great architectural solution.In a professional development project, you must do the following things:
* **Define** the customer requirements for the solution.
* **Design** a great solution to meet those requirements.
* **Implement** the designed solution.
* **Test** the solution implementation.
* **Validate** the solution with your customer.
* **Deliver** the solution in the working environment.
* **Maintain** the solution afterwards.

Software engineering defines these activities as the software development lifecycle fundamentals. All the theoretical software development process models (waterfall, spiral, incremental, agile, and so on) are somehow related to this cycle.

The main point about designing great solutions is foundational to the purpose of this book. You must understand that great real-world solutions bring with them a few fundamental constraints:
* The solution needs to meet user requirements.
* The solution needs to be delivered on time.
* The solution needs to adhere to the project budget.
* The solution needs to deliver good quality.
* The solution needs to guarantee safe and effective future evolution.

## Software Development process models
It is important for you to understand some of the common development processes that are currently used in most enterprises. A software development process defines how people in a team produce and deliver software. In general, this process relates to a software engineering theory, called a **software development process model**. Ever since software development was first defined as an engineering process, many process models for developing software have been proposed. Let us review the traditional software models, and then look at the agile ones that are currently common.

### Reviewing traditional software development process models
Some of the models introduced in software engineering theory are already considered traditional and obsolete. Like the **waterfall** and **incremental** models.

### Understanding the waterfall model principles
This topic may appear strange in a software architecture book from 2023, but yes, you may still find companies where the most traditional software process model remains the guideline for software development. This process executes all fundamental tasks in sequence. Any software development project consists of the following steps:
* **Requirements**: where a product requirements document is created, and it is the basis for the software development process.
* **Design**: where the software architecture is developed according to the requirements.
* **Implementation**: where the software is programmed.
* **Verification**: where tests are performed in the application.
* **Maintenance**: where the cycle starts again after a delivery.

<kbd>
  <img src="https://github.com/MinenhleNkosi/Software-Architecture/blob/main/Notes/Images/0.%20waterfall.png" alt="WaterfallModel" />
</kbd>
                                              
Often, the use of waterfall models causes problems such as delays in the delivery of a functional version of the software and user dissatisfaction due to the distance between expectations and the final product delivered. Besides, in my experience, having application tests start only after the completion of development always feels terribly stressful.

### Analyzing the increment model
**Incremental development** is an approach that tries to overcome the biggest problem of the waterfall model: the user can test the solution only at the end of the project. The idea of a model following this approach is to give the users opportunities to interact with the solution as early as possible so that they can give useful feedback, which will help during the development of the software.

<kbd>
  <img src="https://github.com/MinenhleNkosi/Software-Architecture/blob/main/Notes/Images/1.%20IncrementModel.png" alt="IncrementModel" /> 
</kbd>


The idea of the model is to run for each increment a set of practices related to software development (**communication**, **planning**, **modeling**, **construction**, and **deployment**). Although it mitigated problems related to the lack of communication with the customer, fewer increments were still a problem for big projects because the increments were still too long.When the incremental approach was used on a large scale—mainly at the end of the last century—many problems related to project bureaucracy were reported, due to the large amount of documentation required. This clunky scenario caused the rise of a very important movement in the software development industry – **agile**.

## Understanding agile software development process models
At the beginning of this century, developing software was considered one of the most chaotic activities in engineering. The percentage of software projects that failed was incredibly high, and this fact proved the need for a different approach to deal with the flexibility required by software development projects.In 2001, the Agile Manifesto was introduced to the world, and from that time forward various agile process models were proposed. Some of them have survived up until now and are still very common.

One of the biggest differences between agile models and traditional models is the way developers interact with the customer. The message behind all agile models is that the faster you deliver software to the user, the better. This idea is sometimes confusing for software developers who understand this as – **Let’s try coding, and that’s all, folks!** However, there is an important observation of the Agile Manifesto that many people do not read when they start working with agile:
