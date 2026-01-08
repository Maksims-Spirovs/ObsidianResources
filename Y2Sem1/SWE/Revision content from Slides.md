Week 1:
	Why would large software projects fail?
		Lack of end-user engagement
		Poor communication, both internal and external
		Poor config management
		Not enough/poor testing
		Poor management
		Technical complexities and their issues
			All result in poor quality 
			late delivery 
			excessive costs
	Engineering definition - 
		Application of scientific and mathematical principles to practical ends
			Spheres of design, manufacture, operation of efficient and economic
			structures, machines processes and systems
		General activities include:
			Managing, modelling, testing and maintaining
	Software engineering definition - 
		Systematic application of scientific and technological knowledge
		applying to many principles,
		 from sound engineering, 
		 production of computer programs, 
		 requirements definition, 
		 functional specification design description,
		program implementation, 
		testing methods to lead up to the code.
			With software, the major cost/effort is in design, not manufacturing
			Faces inevitable novelty
			Discontinuous behaviour
			Changes are easy and cheap but may have side effects
Week 2:
	System definition: 
		Arrangement of parts/elements that when combined together
		exhibit a certain behaviour that individual parts would not be 
		able to produce.
	Functional boundary of the system definition:
		Mechanical, electrical, mass, thermal, data and procedural flows as 
		presented in the form of interface constraints, and its interactions with
		the system, expressed in form of system's response to stimuli and user/
		environmental behaviours within expected system behaviours in quantitative terms.
	Abstract arrangement of a system:
		Key Inputs, Key Outputs, Physical Components and Conceptual Components
		Examples:
			Company Payroll:
				Key Inputs: Employee Information
				Key Outputs: Payslips/cheques/cash
				Physical Components: People, paper, computers
				Conceptual Components: Pension Fund
			London Underground:
				Key Inputs: passengers, funds
				Key Outputs: passengers, fuel emissions
				Physical Components: Trains, Drivers, Track, Signals
				Conceptual Components: Routes, Timetables
	General Properties of a system:
		Made up of components, consisting of both physical and conceptual
		Receives inputs that, via the use of processes, produces outputs
		Exists within an environment
		Boundaries provide divisions that separate things from inside the system
			from the outside
		Exhibits behaviours, both expected and potentially unexpected
		Fulfils a specific purpose, could vary depending on viewpoints
	Modelling System definition:
		Process of developing abstract models of a system, with providing
			different perspectives and views of the system
		In order to be able to effectively communicate system requirements to
			both stakeholders, business and IT alike, it needs to be accounted
			for that models should have a variety of perspectives. These models
			provide basis for a more elaborate and detailed design.
		Including:
			External Perspective:
				Modelling the context/environment of the system
			Interaction Perspective:
				Model the interactions between a system and environment/
					between different components of the system
			Structural Perspective:
				Model the organisation of a system or the data that is handled 
					by the system
			Behavioural Perspective:
				Modelling the dynamic behaviour of the system and how it would
					respond to events
		Methods include:
			Flowcharts, DFD (Data Flow Diagrams), Formal Methods, OO Methods
				consolidated in UML, story driven modelling (OO modelling for AGILE)
	UML Diagrams to represent essentials of a system:
		Activity Diagrams: 
			Show activities involved in a process/data processing
		Use-Case Diagrams:
			Show interactions between the system and its environment
		Sequence Diagrams:
			Show interactions between actors and system and system components
		Class Diagrams:
			Show object classes in the system and associations between the classes
		State Diagrams:
			Show how the system reacts to internal and external events
		UML is used as its an industry standard for software engineering
		Integrates design, documentation and implementation into one
		UML class defines:
			Name: 
				Car
			Attributes:
				model : string
				numberOfDoors : int
				color : string
				wheelBrand : string
			Methods:
				+changeColor()
				+changeWheels(brand : string)
			Methods feature a signature:
				visibility (public/private)
				stereotype (enum/entity/any sub form of a class)
				operation-name (name of a method)
				parameter list (newly defined attribute that may reference existing ones)
				return value (expected datatype - boolean, int, string, etc. )
	Model Driven Development:
		+Increase dev speed
		+Increase software quality
		+Better management of complex software via abstraction
		+Design reusable systems
		-Takes additional time and effort
		-Expertise in modelling and design 
	Object Orientated Development:
		Based on identifying:
			Objects 
				Entities including physical (car), conceptual (pension fund) and software (Linked List)
				Instance of a class 
			Classes 
				Description of a group of entities with common factors like attributes (properties), Behaviour (methods), Relationships and Semantics
				A form of abstraction in the form of emphasizing relevant characteristics and also supressing irrelevant ones
				Abstract definition of an object - defines behaviour of each object in class and a template for creating said objects
				Features a hierarchy:
					Superclass - common attributes, associations and operations
						(Account)
					subclass - specialised form of a class
						(Savings Account)(Checking Account)(Mortgage Account)
					Hierarchy features one or more generalisations is an inheritance hierarchy
				Generalisation - relationship between a subclass and its immediate superclass
				Specialisation - subclass in question in relation to generalisation
			Attributes
			Members
			Relationships between objects
				All applies to specification, design and programming
	Attributes and Associations
		Attribute - named property that holds a value inside a class
		Association - explicit relationship link between 2 classes where
			the instances are explicitly connected 
		Example:
			Rectangle: (public class Rectangle)
				height : double
				width : double
				(...getter and setter methods for both...)
			Square: (public class Square extends Rectangle)
				association of a rectangle
			Therefore every Square is a Rectangle and features the 
				same attributes and methods
		A subclass inherits all the members like fields/methods/nested classes
			from its superclass, for the exception of constructors as they are not
			members, however a constructor of the superclass can be invoked from
			the subclass 
		This allows to avoid duplication and improve reusability of members
		However to maintain its usability:
			Do not name sub/superclasses ambiguous names
			Subclass must retain distinctiveness through its life
			Inherited features must make sense in each class
				Otherwise it might cause more trouble than lack of inheritance would've done!
	Abstract classes and methods:
		Abstraction - process of hiding the implementation details and only presenting 
			only the functionality to the user
		Abstract class - A class that needs to be declared as abstract and may feature abstract 
			methods. They cannot be initialised but can be subclassed
		Abstract method - method that is declared without an implementation
		Example:
				public abstract class Shape{
				abstract int getPerimeter(); 
				}
				public class Rectangle extends Shape{
				int getPerimeter(){
				...}
				}
		*a shape is an abstract class, however we never gonna need to initialise shape as its not going to be used by itself, however it will be a medium for actual shapes like rectangles that will use it as a superclass and borrow from its methods, for example getting perimeter of a shape, not needing it to declare for every shape (rectangle, triangle, circle, etc) but instead using one abstract class to always call back on it, useful for saving memory, space and general ease of use*
	Interfaces:
		Real world analogy: 
			Software engineers will agree to certain contracts detailing how their software interacts, and should be able to write their code without knowledge of how the other group is writing their code - interfaces are programming representations of that
		Reference type akin to a class that only contains:
			Constants
			Method Signatures
			Default Methods
			Static Methods
			Nested Types
		Method bodies only exist for default methods and static methods
		Cannot be initialised
		Only implemented by classes or extended by other interfaces
		Example:
			public interface Shape{
				public void getPerimeter();
			}
			public class Rectangle implements Shape{
				Public void getPerimeter(){
				...
				}
			}
		*its different from an abstract class despite looking pretty similar in terms of Java implementation. An abstract class cannot be initialised and usually contains a mix of abstract and not implementations that are meant to be overridden for use by respective subclasses. Abstract class uses generalisation (formally isA) as a shared implementation. Should be used to form a hierarchy and share key features of common code/fields, like abstract class Shape that would be used to generalise shapes like rectangles, circles, etc with a shared color, position and potential default methods.
		 However an interface represents a set of operations forming a behavioural contract without a state, and classes that use the interface are to realise it. Interface use realisation that implements instead of generalising. Should primarily be used when modelling a capability/role, for example what an object should do like 'can-draw', 'can-log', etc to multiple unrelated classes that should be able to adopt those features*
Week 3:
	Class associations:
		Class multiplicity:
			0: zero, 1: one, * : many, 0..* (interval/range)
			Examples:
				Employee *  (worksFor) ---> 1 Company   (assoc name)
				AdminAssist * ----> 1...* (supervisor) Manager (role name)
				Company 1 ----> 1 Board of Directors
				Office 0..1 (allocatedTo) ----> * Employee
				(boardMember)Person 0,3...8 -----> * boardOfDirectors
					1:M - M side can be optional if not specified
					M:M - Both can be optional if not specified
					1:1 - Both must exist at the same time
			Associations may have properties indicating order and uniqueness
				:: 'ordered' | 'unordered'
				:: 'unique' | 'nonunique'
					Student * (courses(ordered, unique)) (enrolledTo) -----> * (students) Course
				Collections are not ordered by default, needs to be specified if multivalued, thus being sequentially ordered
				If is multivalued and unique, then each value in instantiation of the collection must be unique, thus each value in collection is unique 
			Semantics/real application of class multiplicity:
				A booking is exactly for one passenger, passenger can have any number of bookings, a booking is always for one specific flight, specific flight can have any number of bookings
					Passenger 1 -----> * Booking * -----> 1 SpecificFlight
		Association Classes:
			In cases where its uncertain where a value needs to be stored, for example:
				In which class should the students' grade be put? 
					Student * (isRegisteredIn)----> * CourseSelection
				In cases as such, both are valid, but an association class can also be used
				Student * (enrolledIn)----> * Module
					Transcript Item(enrolmentData, finalMark)  
			In (pseudo)Java:
				Set</Transcript/> transcriptItems;
				...
				class Transcript Items{
				student ( * Student )
				module ( * Module )
				enrolmentData;
				finalMark; 
				} 
		Reflexive Association:
			Association to connect a class to itself
				asymmetric: different roles at each end
				symmetric: same roles
					* (successor) --Course * <---> * (isMutuallyExclusiveWith)
								|    | 
								 ---  * (prerequisite)
		Directional Associations:
			Bi-Directional: 
				Data can travel back and forth
			Uni-Directional:
				Can travel one way, not the other
			Day (day) X--> (notes) 0..* Note
			PseudoJava:
				...
				**private** ArrayList</Note/>notes: 
				X---> **public** class Note{...}
		Aggregation:
			A class is a part of the aggregate/aggregate is composed of the parts
			(Vehicle is an aggregate of car parts - car parts may exist by themselves but a car cannot exist without the parts)
			If something controls the aggregate, it also controls the parts of which its made
		Composition:
			Similar to aggregation, but stronger, where if aggregate is removed then the parts are removed alongside it
			(An office is a composition of rooms, if the rooms are destroyed then office is subsequently also gone)
				In aggregation a child can outlive the parent class, however with composition the child's lifecycle is dependant on the parent's class instance
			Aggregations provide for better encapsulation.
	Dynamic Model:
		Interaction diagram models like sequence and communication diagrams are for system execution
		State/Activity diagrams are for system behaviour
		|
		Sequence Diagram:
			Features actors (users and anything that interacts) 
			Objects (classes and things that get interacted with)
			Activations (root of objects where other objects/actors interact)
			Message (arrows connecting different activations)
				Async messages, sync messages and response messages
			Combined fragment(selected out window that gets activated on argument activation)
			Argument (condition that needs to be met to activate guard responses)
		State Diagram:
			Features start states (beginning)
			End States (end result of conditions)
			Transitions (arrows going between conditons/end states)
				Time transitions (after 25s, etc)
				Condition transition (classSize >= maximum)
			State computations
				Activity (does anything happen in the state)
					Occurs over a period of time and while sys is in a state
					If activity complete, out of state
					If other transition triggerd first, sys terminates the activity as it leaves the state
				Action (what happens in the state within activity)
					Effective instantly, when sys takes a particular transition
					Upon entry into a particular state, no matter which transition
					Upon exit from a particular state, no matter which transition
					Actions include send a message, create, destroy
			Nested states
				Substate/nested state: state inside another state (inner diagram)
				Composite state: States with multiple states 
Week 4:
	Domain Analysis and Design:
		Analysis: What softw should do - functionality and properties
		Design: How it does it 
		Domain: Collection of current/future sofw applications that share a set of common characteristics that precisely describe series of problems that the application is going to solve.
		Domain Analysis:
			Process of identifying, capturing and organising data used for softw development, with domain meaning general field of business/tech in which customers are expected to use the softw
			It is necessary for faster development, higher quality systems, management of extensions and reusability (primarily around analysis and design rather than code).
			If correctly identified, can be used to build new system/features based on current ones, thus allowing for a more reusable software.
		Example:
			Introduction:
				Background information that has been gathered about X in Y and how its handled. Information is used to guide development of Z to automate the process of achieving goal of X.
			Glossary:
				Event - {definition}, which can also split into categories:
					Open event - {definition}
					Fixed Event - {definition}
					Day events - {definition}
						Recurrent event - {definition}
						Composite event - {definition}
			General knowledge about the domain:
				{Timescopes of events}
				{Location}
				{Person of interest}
				{Group of interest/target audience}
				{Outdated information is of little interest}
				{Metadata (events have a title, location, and person of interest)}
				{Security concerning the domain}
			Clients and users:
				Target audience - medium or large companies that perform a certain type of related work. Smaller target audience include:
					Employees of all levels and potential users of related X software. From novices to seniors.  
					Sys admin managing computer environment
					Technicians to install softw
			Environment:
				Actors have computers, usually ms-windows, but minority may use other platforms.
				Wide variety of unique config sofw on computers, some softw may be installed using site-wide license
			Tasks performed:
				{Informing others, outside of the company}
					{Ways and approaches to achieve the task - informing via different ways}
					{Weigh the different ways suggested}
					{Acknowledge positives and good of the weighed solution}
			Competing software:
				{Weigh the benefits, conflicts and handling of potential pushback or currently present alternatives}
		Domain Model:
			An object of the domain that includes both behaviour and data
				Created to represent vocab and key concepts of problem domain
				Identifies relationships and attributes among entities within scope of domain problem
		Requirements analysis:
			Studying user needs to arrive at a definition of requirements for systems, hardw or softw
			Studying and refining the sys, hardw or softw
			Identify stakeholders
				Persons with a valid interest in the system or affected by it
				Anyone who operates the sys (users/maintenance)
				Benefits from sys in any way
				Involved in purchasing or procuring the sys
				Organisations that regulate aspects of sys 
				Organisations responsible for systems which interface with system
				Negative stakeholders - persons/orgs opposed to the sys
			 elicit requirements
				  Interviews to find the requirements, but factors to look out for:
					Scope 
						  Boundary of sys, what details are required
						  Usually at the beginning to understand the project, and features that may need inclusion to meet stakeholders requirements
							  Project Scope - Work needed to deliver product/service/result with specified features/functions
							  Product Scope - Features/functions that characterise the product/service/result
						Watch out for feature creep/ requirements or scope creep
							Requirement def
								Condition/capability needed by a user to achieve obj
								Cond/capa that must be met/the sys (component) has to satisfy the needed feature/other kind of imposed doc
								Aspect of what proposed system must do
								Constraint on sys dev
								May be functional 
									Everything user would need to know regarding what the system does
									Everything that would concert sys that needs to interface with ours
								or non functional
									Many things that are needed for optimal operation but not vital for minimal operation of the system
									Clear outlines, like timescopes for maintenance windows
								Basic issue of requirements:
									Functionality - what does it do
									External interfaces - How does it interact with people, sys hardw, other hardw/softw
									Performance - speed, availability, response time, recovery time
									Attributes - portability, correctness, maintainability, security, etc
									Design constraints - Required standards? Implementation lang? Policies for database integrity? resource limits? operating environments? etc
								Styles of req:
									Contract - full contract between client/dev, hundreds of pages, abstract all req with little context
									User stories/use cases - AGILE dev, capture a desc of softw feature from end user pov, context present, short
									Use Case analysis
										What user should be able to do with your softw
										Sequences of actions that a sys/subsys/class can do by interacting with outside actors, done by presenting a behaviour without revealing internal structure, determines types of users and tasks for them
										Includes:
											Name, Actors, Goals, Preconditions, Summary, Related use cases, Steps, Post Conditions
										+Define scope of sys
										+Plan dev process (potentially indicates size)
										+dev and validate requirements
										+define test cases
										+structure user manuals
										-less understanding of domain/real problem
										-requirements can change quick
										-attempting to do too much
										-difficult to reconcile conflicting sets of reqs
										-hard to state precise reqs
					Understanding
						Users wont know what they want, is needed, potentially their environment and of the domain
					Volatility:
						Requirements may change overtime
					provide prototypes
Week 5:
	System Design:
		Defining architecture, models, interfaces and data for system to meet requirements, with principles including:
		Modularity:
			Breaking a complex system into smaller, manageable parts
			Separates concerns, allows for independent dev, easier testing and maintenance, lighter damage control and reusability
		Abstraction:
			Simplified representation of something complex
		Encapsulation:
			Hiding complexity of internal workings of the object hidden
		Hierarchy:
		Systems and components can class as:
			Systems, Subsystems, Packages, Classes and Methods	
		Cohesion - extent to a which a component has a clear purpose/function
			Functional: 
				Facilities are kept together that perform one computation with no side effects, everything else is out of picture
			Layer:
				Related services are together, all else out. Has hierarchy where higher level services can access lower level, accessing which may cause side effects
			Communicational:
				Facilities for operating on same data are together, all else out. Good classes exhibit communicational cohesion.
			Sequential:
				Set of procedures working to perform a computation work together. Output of one is input to next. All else out.
			Procedural:
				Procedures called one after another are together. All else out.
			Temporal:
				Procedures used in the same general phase of execution, like initialisation/termination are together. All else out.
			Utility:
				Related utilities are together, when there is no other way to group them with stronger cohesion.
				+Easy to understand, less complex modules
				+Easy to maintain
				+Reusable
		Coupling
			Level of interaction between components in a system
			A component like OrderHandler may depend on class Order, so changes to Order may result a need to change OrderHandler
			Loose coupling:
				Components with few connections to each other, connected to at least one module
			Tight coupling:
				Components with many ingoing and outgoing connections to each other
			Types include:
				Content - a component unnoticeably changing contents of another component - avoid!
				Common - Use of global variables - restrict the use of
				Control - One procedure manipulates the other using a flag - reduce with polymorphism.
				Stamp - One argument type of a method is one of application classes. Simplifies the system, replace such args with simpler args (like interface, superclass)
				Data - Use of method args that are simply data. Reduce number of args if possible
				Routine Call - Routine calling another. Reduce total num of separate calls by encapsulating repeated sequences.
				Type use - Use of a globally defined dt. Prefer simpler types (interface, superclass)
				Inclusion/Import - Incl a file/Import a package. Elim where not needed
				External - Dependency exists to elements outside of scope of sys, like OS, shared libs or hardw. Reduce number of places that have dependencies on external factors.
			+Easy to understand
			+Better maintainability
			+Relatively better reliability
			Systems should be decomposed at each relevant level of abstraction into components that have high cohesion, resulting in low level of coupling.
		Abstraction:
			View of object that focuses on information relevant to a particular purpose, ignores remainder of info - reduce complexity, allow efficient design and implementation
			Important to find right level of abstraction, don't always need to go to the lowest level, just enough that there is a clean separation of concerns to reinforce organisational structure. Need to keep in mind the level of detail, as to not get rid of too much to sweep the problem away, and not to keep too much to obscure the problem.
		Encapsulation:
			Dev technique that isolates sys func/set of data and ops on data within a module and providing precise specifications for the module.
			Information hiding:
				Interfaces reveal as little as possible about inner workings, other modules can't use information that is not included in interface spec.
			Bundling data with methods that operate on that data - restricts access to some of the components.
			Example:
				public class Dice{
					public final int numberOfSides = 6
					private int numberRolled;
					public int roll(){
						numberRolled = new Random().nextInt(numberOfSides);
						return numberRolled;
					}
					public int getNumberRolled(){
						return numberRolled; 
					}
				}
			Hiding internal workings by separating interface and implementation:
				Simplified and understandable way to use object without the need to understand complexity
			Because inheritance exposes a subclass to details of parent's implementation, inheritance breaks encapsulation
			If derived class can access members inherited from base class, changes in base class may require maintenance of derivatives.
			Liskov Principle - all derived classes must be substitutable for base classes
				If var type is a superclass, then program should work properly if you place an instance of superclass or any of its subclasses in the var - program using the var shouldn't be bothered by what class is being used
			Dependency inversion principle - Classes should only depend on abstraction
				In trad dev, high level components depend on low level ones, making them difficult to reuse. High level modules should be reusable and unaffected by changes in low level. So need abstraction to decouple high level/low level modules from each other. 
				High level don't depend on low level, both depend on abstractions, that themselves should not depend on details but details should depend on abstractions.
			Open/Close principle - Open for extensions, close for changes
				If still available for extension, like add fields to the ds it contains, or new elements to the set of funcs it performs. Closed if available for use by other modules, assuming given a stable description (interface). Achieved via inheritance and dynamic binding - new func added by adding new code, not editing old.
Week 6:
	Design Patterns:
		Recurring solutions to design problems that you see recurrently
			To become better - learn rules, learn principles and then study masters designs
		Creational patterns:
			Creating, initialising and configuring classes and objects
				Abstract Factory:
					Interface for creating families of related/dependant objects without specifying concrete classes
				Builder:
					Separate the construction of a complex object from its representation, allowing the construction of it to create more representations
				Factory Method:
					Interface for a single object, subclass decide which class to instantiate. Defers instantiation to subclasses (dependency injection)
				Lazy initialisation:
					Delaying creation of an object, calculation of a value or other costly process until its needed for the first time. Virtual proxy/implementation for the proxy pattern
				Multiton:
					Ensure a class has only named instances and provide a global point of access to them
				Object Pool:
					Recycle the objects that are no longer in use thus avoiding expensive acquisition and release of resources. Generalisation of connection pool/thread pool 
				Prototype:
					Specify kinds of objects to create prototypical instance, and create new off previous prototypes
				Resource acquisition is initialisation:
					Resources are properly released by tying them to lifespan of respective objects.
				Singleton:
					A class has only one instance, there is a global access point for it
		Structural patterns:
			Decoupling interfaces and implementations of classes for a more powerful structure
				Adapter/Wrapper/Translator:
					Convert interface another expected interface. Allows classes now can work together that previously couldn't because of incompatible interfaces. 
				Bridge:
					Decoupling abstraction from its implementation, allowing them to vary independently. 
				Composite:
					Compose objects into tree structures to represent part whole hierarchies. Treating individual objects and compositions of objects uniformly.
				Decorator:
					Attach additional responsibilities to an object dynamically while keeping the same interface. Flexible alternative to subclassing for extended functionality.
				Facade:
					Unified interface to a set of interfaces in a system. Higher level interface to make subsystems easier to use.
				Flyweight:
					Sharing to support large number of similar objects efficiently.
				Front Controller:
					Centralised entry point for handling requests.
				Module:
					Group related elements like classes, singletons, methods, globally used into a single entity.
				Proxy:
					Placeholder for another object to control access to it
				Twin:
					Allows to model multiple inheritance in programming languages that don't support a feature
		Behavioural patterns:
			Communication between group of objects and classes
				Blackboard:
					Observer allowing for multiple readers/writers. Communicates info sys wide
				Chain of responsibility:
					Avoid coupling to sender to receiver by giving more than one object a chance to handle request. Chain via objects and pass the request along the chain till end object handles it.
				Command:
					Encapsulate req of an obj, parameterise clients with diff req, queue or log reqs, supp undoable operations.
				Interpreter:
					Interprets using a language for its grammar that uses the representation to interpret sentences in the lang.
				Iterator:
					Access elements of aggregate obj sequentially without exposing underlying representation
				Mediator:
					Obj that encapsulates how a set of obj interacts. Loose coupling as obj are not referring to each other explicitly, vary interactions independently.
				Memento:
					Capture and externalise obj internal state without violating encapsulation, state can be restored to normal state later.
				Null obj:
					A default object allowing to avoid null references
				Observer:
					One to many dependancy between obj where a state change in one obj results in all dependants being notified and updated.
				Servant:
					 Common functionality for a group of classes
				Specification:
					Recombinate business logic in boolean
				State:
					Allows obj to alter behaviour when internal state changes, obj will change its class
				Strategy:
					Family of algos, each one encapsulated, interchangeable, algos can vary independently 
				Template method:
					Skeleton of an algo in an operation, deferring some steps to subclasses. Allows subclasses to redefine certain steps without changing structure.
				Visitor:
					Represent operation to be performed on elements of obj structure. Define new operation without changing the classes of elements on which it operates.
	Elements of a design pattern:
		Name - title that conveys essence of a pattern
		Context - situation in which the pattern applies
		Problem - Statement of the problem that describes the pattern's intent and issues to consider
		Solution - Elements that make up the design - relationships, responsibilities and collaborations
		Consequences - results and trade offs of applying pattern
		Antipattern - Examples of bad practice if you don't use it
	Abstraction-Occurrence - Problem:
		Context - set of related objects whose members share common information but differ in important ways
		Problem - Efficient way to implement set of objects without duping common info
			<</Abstraction/>> 1 ---> * <</Occurrence/>>
			Contains common to all related items
				Contains info that is unique to instances of items
	Singleton Pattern - Problem:
		Context - common to find classes for which only one instance should exist
		Problem - Ensure not possible to create more than one instance, use of public constructor cannot guarantee that no more than one will be created, must be accessible to all classes that require it
		Solution - Private static instance, private constructor prevents creation of instances from outside the class, public static method to get the instance
	Iterator Pattern - Problem:
		Context - traversing an aggregate object
		Problem - Traversing might expose the representation (ds) of aggregate obj, traversal methods might be changed which will change the client code (interface)
		Solution - Separate iterator to encapsulate accessing and traversing an aggregate obj, clients use an iterator to access and traverse an aggregate without knowing its encap, new access and trav operations can be defined without changing interface
	Model View Controller Pattern:
		Context - GUI to interact with core program logic
		Problem - Logic is intricately dependant on GUI rep of it, then change becomes difficult if multiple different views needed. Make the gui and logic as indep as possible
Week 8:
	Software Life Cycles:
		Phases include:
			Requirements capture/analysis
				Identify and agree on general (non)-functional requirements
				Prioritise requirements
				Discuss risk analysis, cost factors, development scheduling
				How primary users might test the system
				Identify changes that mind be needed and how to implement
			Specification
				What does the sys do - not how it does it
				Formal version of requirements written by a dev
				Filtering of errors, omissions and impracticalities from requirements phase
				Solidify functional and performance requirements
				A formal contract that should be understandable by a primary user
				Detailed plan for acceptance test
			Design
				{I already talked plenty about design ;-; }
			Implementation
				Process of expressing the detailed design in a programming language so it could run on the target system
			Testing
				Unit testing
				Integration Testing
				System and acceptance testing
				Regression testing
			Deployment
				A functional version on a target system
				Release all needed support and manuals
				Coordinate with hardware
				More acceptance testing
				Training and support teams
				Evaluation of the project
			Maintenance
				Corrective, adaptive, perfective and preventive 
			Documentation
				Requirements docs
				Architecture/Design docs
				Technical docs
				End user docs
				Marketing docs
		Types of life cycle models:
			Build-and-fix
				Poor model - 
				NO specifications, NO design
				High cost and difficult to maintain
			Waterfall
				The aforementioned:
					Requirements, spec, design, implementation, testing, deployment and maintenance
				+Disciplined approach
					-Documentation for each phase, QA checks for each phase
				+Easier maintenance 
					-Every change is documented 
				-Working version won't be ready till late in the project lifespan
				-Specifications are long and detailed
				-Blocking states - certain team members gonna have to wait for others to finish their work before starting theirs
				-No prototypes - harder to gather requirements
					-Commonly bad! 18% fail, 53% late, over budget or descoped
			Formal transformations model
				Requirements, Formal spec, refinement 1, refinement 2... refinement n (source code), executable code
				+Precise
				+Often used in safety critical systems
				-Requires expertise 
				-Higher level of complexity
				-Costly and may be prone to errors with excessive verification and testing
			Prototyping
				Requirements capture, Specification (Prototype Implementation, to testing, back to requirements capture), Design, Implementation, Testing, Maintenance
				Rapid prototyping:
					Models are often discarded instead of becoming part of final product. After initial requirements gathering a first model is produced to show users basic functionality and what requirements may look like when implemented in a finished system.
				Evolutionary prototyping:
					Robust prototype that gets constantly refined. Core piece of the final system, improvements and further requirements are built around it.
				Incremental prototyping:
					Final product is built as separate prototypes, at the end the prototypes are merged into one final design.
				Extreme prototyping:
					Static prototype consisting of html pages, then fully functional UI with a simulated services layer, then the services are implemented.
				+Reduced time and costs
				+Speedy and accurate due to user involvement
				-Clients may be disappointed
				-Developers may not get attached, difficult to focus 
				-May be excessive in time and effort in terms of costs
			incremental process model
				Simple working system is built initially then given to customer. Then many successive versions are built, implemented and delivered until the customer is satisfied. Relies on customer feedback for each version, and feedback is implemented in successive versions, each having more features than previous.
					Staged delivery model - construction of only one version at a time
					Parallel delivery model - Different subsys are developed at the same time (parallel)
				+Faster Dev
				+Client involvement
				+Easier change implementation
				+Improved risk management
				-Harder to manage
				-Increased cost due to iterations
			Iterative Development:
				Waterfall development but executed in phases, returning back to requirement capture after each trial
				+Customer feedback due to early working software
				+Requirements and spec in phases
				+Procedural improvement allows to track defects
				-Requires careful planning as early mistakes can impede on future evolutions
				-Difficult to switch methodologies and languages as phases increment
				-Not having complete requirements results in major problems down the line
			Unified Process (UP)
				Inception, Elaboration, Construction and Transition
				Structures the project as a number of phases
				Each phase has iterations
				Different activities are performed at each iteration
				Inception:
					Project scope and boundary conditions
					Use cases and key requirements
					Outlines one or more candidate architectures
					Identifying risks
					Preliminary project schedule and cost estimations
				Elaboration:
					Capture reqs
					Design softw architecture
					Planning for construction phases
				Construction:
					Build using the UML diagrams
				Transition:
					Deployment of initial release
					Feedback reports on defects and changes
				+Documented with complete methodology
				+Adaptable to easily changeable requirements
				+Reduced integration time and effort
				+Higher reusability
				-Incredibly complex
				-Not natural code development
				-Disorganised development
				-Continuous integration is challenging
			Spiral Model
				Incorporates waterfall and prototyping
				Number of spirals (loops/waterfall iterations) is dependant on project risks
				+Realistic for large scale models
				+Prototyping to reduce risk
				+Iterative and incremental approach
				+Reduced risk
				-Requires expertise in risk assessment
				-Not fully proven due to reduced employment
				-Requires heavy expertise in risk assessment
			Agile Models (general assessment):
				Alternative to traditional project management
				Used to help businesses respond to unpredictability
				Philosophy:
					Customer satisfaction and early incremental delivery of software
					Small, motivated project teams
					Informal methods
					Minimal sofw eng work products
					Simplified development
				Development guidelines:
					Stress delivery over analysis and design
					Continuous communication between developers and customers
				Manifesto:
					Individuals and interactions between processes and tools
					Comprehensive software takes less priority than working software
					Customer collaboration over contract negotiation
					Respond to change over sticking to a plan
				Agile risk remains about the same as opposed to waterfall that has the risk increasing over time, as agile has early prototypes allowing to snoop out the risks as they come, as opposed to waterfall that receives less overall user feedback, only one integration and the working version releases late
				Models include: XP, Adaptive software dev (ASD), Dynamic System Development Method (DSDM), Scrum, Crystal, Feature driven dev (FDD), Agile Modelling (AM)
				Agile project planning splits into 3:
				Stories:
					User Stories, short requirements/requests written from the perspective of end user
						Description of one or more sentences in everyday/business language of end user/to capture what they need/to do as a part of their function
						Project planning based on US, stakeholders working together to determine which stories are released in each iteration 
							-As a </role/> I can </action with sys/> so that </external benefit/>
					Epics - larger bodies of work embodying the user stories, break down into at least 1 user story
					Initiative - collection of epics driving towards a common goal
				Agile may have issues!
					Scaling
					Technical debt as a result of faster releases
					Harder priority management - they change over time and people are generally not good with managing priorities
					Product backlog - ordered list of everything known and needed in the product
					Sprint backlog - tasks identified in a scrum to be completed during a scrum sprint
			Extreme Programming (XP)
				Small releases, simple design, testing TDD, Refactoring, Pair Programming, Collective ownership, continuous integration, code according to standards
				Planning -> Design -> Coding -> Testing (-> back to Planning) -> new release (increment n)
				Planning:
					Initial brief prototype
					Scope out next release
					Put simple sys into prod, then release new versions on quick cycle
					Short but frequent meetings
					Continuous client involvement
					No burn out (hopefully)
					Frequent change
				Coding:
					Prod code written by two programmers on one machine?
					Code can be changed anywhere at any time
					All code written to agreed standards with consistent communication 
				Testing:
					Unit tests for each method before even starting coding
					Tests provide definition and documentation for required behaviour
					Integrate and build a system every time a task is completed
				Should be written as simply as possible, extra complexities removed as soon as discovered, to maximise that look for well known design patterns and refactor (changing softw sys that it doesn't alter the behaviour yet improves structure)
			Scrum
				Iterative and incremental framework for product dev
				for small teams to break work into actions, completing work within timeboxed iterations (sprints), usually 2 weeks but no longer than 1 month, progress tracking/replanning done in scrums - brief meetings 
			To determine which SDLC to choose
				Size of proj
				Complexity of prod
				Familiarity with prod
				Size of team
				Likelihood of changes
Week 9:
	Software Testing
		Why do it?
			Demonstrate to dev and customer that softw meets reqs
			Discover situs in which behaviour is incorrect/undesirable and/or not conform to spec (defects)
		What is it?
			Execution of softw for validation/verification, with possible intent of finding errors, evaluating an attribute/capability of a program/sys and determining whether it meets specified results, usually with interests of providing stakeholders with info about the product/service under testing
		Bugs
			A failure, or any sort of unacceptable behaviour exhibited by the system, bugs are a specific flaw in an aspect of a system incl the requirements or code design that may contribute to at least one or more failures
			An error is a slip-up made by the developer that could lead to the introduction of bugs/defects to the system
		Test Case
			Required test data (inputs) and knowledge of expected outputs
			Usually in form of a tuple (i,o) where the test data and o=S(i) for S (software under test)
			examples:
				Input (i) = test
				Expected output (o) = TEST
				Test Case = (test, TEST)
				Test Me
				error
				Test Case = (Test me, error)
				etc etc.
			Integration and sys testing focus on testing interactions between components and objects that make up the sys
			Can't test absolutely everything, including the most trivial of things as it requires costs and efforts and may result in excessive halting 
			Standard approach requires:
				Write a piece of code, write a driver (activator of code) and include print statement or whatever preferred form of output and ensure that it fulfils the needed function. Repeat until satisfied (never)
				Involves test cases, test data, test results and ultimately reports 
			Good testing requires skills and expertise, done by independent testers to eliminate bias, programmers are more likely to stick to data sets that align with the program working, and may not work when tried by somebody else
			Best testing involves finding out as many defects as possible using the fewest number of sets - high yield testing
			Dynamic Testing
				Functional testing 
				Non Functional testing
					Performance
					Stress/load
					Usability
					Security 
			Static Analysis
			Black Box 
				Functional testing - examines functionality of a program without peering into internal structures/workings
				Determining test cases without knowledge of internal logic of softw
				Equivalence partioning
					Every possible program execution sequence is tested
					Exhaustive, all int values (-2^31 to (2^31)-1 ) (suboptimal)
				Boundary value analysis
					Directly choose test cases, above and beneath edges of input equivalence and output equivalence classes
					Example:
						If month checks for numerical month value, so 1-12, check for:
							12,13, 2^31-1 , 2^31
							0,1,12,13
							1,0,-2^31, -2^31-1
				Statistical testing
				Cause-effect graphing
				Error guessing
				Random testing
				Syntax directed testing
				State transition testing
			TDD - Test Driven Development
				Approach to program development in which you interleave testing and code dev
				Dev the code incrementally, along with a test for that increment, dont move onto the next one till that test passes the increment
				Was introduced as a part of agile methods like XP
				Provides code coverage, helps develop a test suite and can be considered documentation
			Integration Testing
				Tests integration/interfaces between components - interactions between parts of a sys like OS, file sys or hardw or interfaces between sys
				After unit testing and before validation testing. Takes input as modules that been unit tested, groups in aggregates, applies tests defined in integration plan to said aggregates, delivers as output the integrated sys ready for testing
				Big Bang 
					Components/Modules integrated simultaneously, then everything tested as a whole
				Bottom Up
					Bottom of control flow upwards, Components/Systems substituted by drivers 
				Top Down
					Following control flow/architectural structure (like starting from GUI) incomplete components are substituted by stubs
				Sandwich
					Combine top down testing with bottom up testing
				Hardest integration testing - 
					Starting with risky/more complex modules first
				Is quite difficult compared to rest due to many issues faced while performing it
					Continuous integration (CI) - merging all dev working copies to a shared mainline - heavily reliant on in XP with integrations taking place several times a day
			White Box
				Testing softw that tests internal structures/workings of an app as opposed to functionality (black box)
				Techniques involve:
					Statement Coverage
						Covers only true conditions
						Identify statements executed and not executed as a result of blockage
						Each line needs to be checked and executed
						+Verifies the code does what it needs to do and doesn't do what it doesn't
						+Easy to measure
						-Cant test false conditions
						-Does not report whether the loop reaches end
					Branch Coverage
						Covers both true and false
						Outcome of decision - measures which decision outcomes have been tested
						+Ensures no branches lead to an abnormality of operations
						+Eliminates the problems that would occur with statement coverage testing
						-Harder to measure 
						-Harder to find set of test suites to cover all branches
					Condition Coverage
							Every boolean subexpr evaluates to true or false
					Modified Condition/Decision Coverage
					Path Coverage
						Executes each possible path in a function
						A path is flow of execution from start to end of a method
						Method with n decisions has n^2 paths, and if it includes a loop it may contain potentially inf paths!
						So if a method has 3 condition statements, and the outcomes are boolean (true/false), that means that path coverage will be 2^3 = 8.
			 Testing in dev:
				 Unit/Module testing
				 Build verif/acceptance testing
				 Integration testing
				 System testing
			Testing after dev:
				Alpha testing
				Beta Testing
				Acceptance testing
				Operational testing (softw in active use)
				Regression testing (can also be done during dev)
			Code coverage:
			Regression Testing:
				Rerunning (non)/functional tests to ensure previously developed/tested softw still runs as intended after changes - Previously working code doesn't malfunction after changes like bug-fixing, enhancements, config changes, as far down as hardware changes
				As suites grow with more defects, test automation is advised and frequently used
Week 10:
	Software Quality:
		What does it mean?
			Degree to which a sys, component or process meets the requirements, user needs and/or expectations.
			Different users may have different perspectives on quality:
				Customers may value acceptable costs in terms of money paid and resources used
				Users may value efficiency of use, ease of learning and to ultimately achieve desired work
				Developers may value ease of design, maintenance and reusability
				Development manager may value more sales, customer satisfaction and overall reduced costs of development and maintenance 
		Quality attributes may include:
			Functionality
				Degree to which softw satisfies stated needs as indicated by suitability, accuracy, interoperability, compliance and security (often to the specification) 
			Reliability 
				Amount of time that softw is available for use as indicated by maturity, fault tolerance and recoverability
			Usability
				Degree to which softw is easy to use as indicated by understandability, learnability and operability
			Efficiency
				Degree to which softw makes use of sys resources indicated by time behaviour and resource behaviour
			Maintainability
				Ease of repair that may be made indicated by changeability, stability and testability 
			Portability
				Ease with which softw can be transposed from one environment to another as indicated by adaptability, installability, conformance, replaceability 
			(The latter 3 are in particular priority from the developers perspective as a part of product revision)
			(The former 4 are a priority from the users perspective as a part of a product in operation)
		Some qualities may come at a expense of the other:
			Efficiency vs Maintainability 
			Reliability vs Efficiency
			Usability vs Efficiency and Maintainability
		Some elements of qualities include:
			Standards - Primarily set by IEEE, ISO and other produced by organisations, those may be adopted voluntarily or imposed by customers and stakeholders
			Reviews/Inspections - Technical reviews/quality control performed by softw eng for other softw eng - in intents of uncovering errors
				For example, group of people may examine the softw, documentation, looking for problems and non-conformance with standards.
					Based on documents made during dev process. Like specs, designs, code, process models, test plans, config management procedures, process standards and user manuals.
					Done to improve softw quality, not assess performance of people.
					A more public form of error detection.
			Testing - {Check previous weeks son}
			Configuration Management - Tracking and controlling changes in softw, like revision control, establishment of baselines and other activities 
			Risk Management - Makes sure that risk management activities are properly conducted and that contingency plans are established
		Verification - Are we building it right?
			Evaluating softw at any point to determine whether the products imposed during a given development phase satisfy the conditions imposed at the beginning of that phase - matches initial expectations 
			Reliant on cross-referencing with other parts
			Development internally is consistently correct
		Validation - Are we building the right product? 
			Evaluating softw during/at the end of development to determine whether it satisfies the requirements
			Reliant on checking in and verifying with the user 
			Demonstrating to the outside that the sys is valid
		Software Quality Models
			McCall:
				![[Pasted image 20260108155315.png]]
			ISO 9126
				![[Pasted image 20260108155403.png]]
			Reliability:
				Probability that sys operates with no failure in a given period of time under operational environment
		Software failure:
			Formal:
				Deviation from specified/expected behaviour
			Engineering:
				Deviation from required/specified/expected behaviour
			Not all faults are equally important!
			More important faults would trigger important failures. 
			Important failures usually make up a very tiny minority of failures, with unimportant failures accounting for a greater chunk of failures but the rest of them would be totally irrelevant
			Most of them are usually benign, and removing most of them may not improve overall quality, with greater priority being from reoccurring faults that lead to reoccurring failures - but never stop looking for them!
		Software Quality Assurance
			Systematic, planned set of actions necessary actions to ensure that softw dev process/maintenance of a sys (product) conforms to functional/technical requirements and managerial requirements like keeping schedule and operating with budgetary confines.
			Fault Avoidance
				SE Methodologies 
				Verification
				Config Management
			Fault Detection
				Testing/Debugging
				Inspection
			Fault Tolerance
				Error Checking/Recovery
				Nth-version programming
	Software Metrics:
		Software Measurement:
			Deriving a numerical value/profile or an attribute of softw component, sys, or process
			Evaluate productivity impacts of new tools/tech
			Establish productivity trends
			Improve softw quality
			Predict future staffing needs
			Predict and reduce future maintenance reqs
		Software Metric:
			Characteristic of softw sys, sys doc, dev process that can be measured in an objective manner.
			Driven by 2 objectives:
				Softw cost/resource estimation
				Softw QC and esimtates
				Quanatitive tools to manage risk in softw projects
		More definitions:
				Measure - Quantitative indication of extent/amount/dimension/capacity/size of an attribute of product/process
				Measurement -  determining a measure
				Metric - Quant measure of the degree to which a sys, component or process possess an attribute:
					Metrics give measures and relate data points to each other
				Indicator - Metric/Series of metrics that provide insight into a process, project or product
				Attribute 
					Length (physical) of the product
					Functionality (functions supplied by product to user)
					Complexity:
						Problem Complexity
						Algorithmic Complexity
						Structural Complexity
						Cognitive Complexity
			LOC (Lines Of Code)
				Simplest and most widely used measure of program size.
				Easy to compute and to automate
				Used for:
					Effort/Cost estimation (Effort = f(LOC))
					QA Estimation (defects/LOC)
					Productivity Assessment (LOC/Effort)
				Similar measures include:
					KLOC = Thousands of LOC
					KDSI = Thousands of Delivered Source instructions
					NCLOC = Non-Comment LOC
					Num of chars/num of bytes 
				Does come with some problems:
					No standard definition 
					Measures length as opposed to size 
					Wrongly surrogates for effort, complexity or functionality
					Doesn't account for redundancy/reuse
					Cannot be used comparatively for different prog languages
					Only development at the end of SDLC
			Albrecht's Function Points:
				Count the num of external:
					Inputs
					Outputs
					Inquiries
					Files
					(Can also include Internal files/interfaces)
					- Each has a weighing factor!
				Unadjusted Function Count (UFC) is the sum of all weighted scores
				To get FP, multiply UFC by Technical Complexity Factor
					FP = UFC x TCF
				 UFC is a sum of i where i is the number of items per parameter
					 Inputs
						 Simple = 3
						 Average = 4
						 Complex = 6 
					Outputs 
						Simple = 4
						Average = 5 
						Complex = 7
					User Inquiries
						Simple =  3
						Average = 4
						Complex = 6
					Files
						Simple =  7
						Average = 10
						Complex = 15
					External Interfaces
						Simple = 5  
						Average = 7
						Complex = 10
				TCF formula
					TCF = 0.65 +(0.01 * (sum of Fi )) (F is functions) (i is func count)
						(The value may vary between 0.65 and 1.35)
				Example:
					Spell Checker Spec:
						Checker accepts **doc** as input and an optimal **personal dictionary file**
						User can **query number of words processed** and **spelling errors found** at any stage
						Files : personal dictionary, doc file 
						Inquiries : num of words, num of errors 
						Outputs : num of words processed, errors found, identified mistakes
							A (external inputs) = 2
							B (external outputs) = 3
							C (inquiries) = 2
							D (external files) = 2
							E (internal interface) = 1
							UFC = 4A, 5B, 4C, 10D, 7E = 58
				One FP should take on avg 2 days
					58fp x 2 = 116 days!
				Used extensively as a size measure vs LOC
				Productivity = FP/Person Months Effort
				Quality = Defects/FP
				Effort Prediction = E=f(FP)
				![[Pasted image 20260108163432.png]]
				a
			Halstead's Software Metrics
				Program (P) is a collection of tokens, classified as operators/operands
					n1 = num of unique operators
					n2 = num of unique operands
					N1 = total occurrence of operators
					N2 = total occurrence of operands
				Measurables:
					Length = N1 + N2
					Vocab = n1 + n2
					Vol = N(log2n)
					Difficulty = (n1/2) * (N2/n2)
					Effort = Volume * Difficulty
					Bugs Delivered = (((Effort * 2) / 3) / 3000)
			Metrics for OO Design
				Size - in terms of Population, Volume, Length, Functionality
				Complexity - like size, has differing views
				Coupling - Physical connections between elements in OOD
				Cohesion - OO components should be designed so that all operations working together achieve a single, defined purpose
				Volatility - Measures likelihood that changes occur
				Intra-package dependencies - high cohesion
				Few inter-package dependencies - low coupling
				Weighted Methods per class  - high WMC = more faults
				Depth of inherit tree - deeper a class in hierachy means more methods and vars to likely inherit, more complex
				Number of Children - NOC - immediate child classes derived from base class
				Higher coupling and WMC = lower quality
			McCabe's Cyclomatic Complexity Metric V
				If G controls flowgraph of program P, and G has 
				e edges (arcs) 
				n nodes 
				In general:
					v(G) = e - (vertices) + 2
				For control flow graphs:
					v(G) = (binaryDecisions) + 1 
					v(G) = (IfStatements) + (Loops) + 1
			Maintainability index:
				171 - 5.2ln(Halstead's Volume)-0.23(McCabe's Cylcomatic Complexity)-16.2ln(LinesOfCode)+50.0sin(root(2.46* percentOfComments))
				![[Pasted image 20260108165429.png]]
			Defect Density:
				num of Defects / sys size (KLOC)
				De facto measure of softw quality
			Goals -> Measures -> Data -> Facts -> Decisions -> Actions
	
	
	
	
	
