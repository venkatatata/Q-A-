# Q-A-
SWIFT 
1. Architectural Patterns & Design:
Explain your approach to designing a scalable and maintainable architecture for iOS applications. (e.g., MVVM, VIPER, Clean Architecture, Redux)
How do you implement Dependency Injection (DI) in iOS apps and what are its benefits?
Describe your experience with SwiftUI. How does it compare to UIKit in your opinion, and when would you choose one over the other?
How do you manage state in a complex SwiftUI application? (e.g., @State, @Binding, @ObservedObject, @EnvironmentObject) 
2. Concurrency & Asynchronous Operations:
How do you handle asynchronous operations in Swift? Have you worked with Combine framework in Swift? If yes, describe its advantages.
Explain how async/await patterns work in Swift and how they differ from Grand Central Dispatch (GCD).
What are Actors in Swift and how do they help with concurrency? 
How do you manage memory when using closures that capture self in concurrent contexts? 
3. Performance & Optimization:
How do you optimize the performance of a Swift application, especially for table and collection views?
How do you identify and resolve memory leaks in iOS applications? What tools do you use?
Explain the difference between map, flatMap, and compactMap and when you would use each for performance or clarity.
4. Advanced Swift Concepts:
Explain Protocol-Oriented Programming (POP) in Swift and how you apply it in your projects.
Describe the use of associated types in protocols and provide a practical example.
What are opaque types and when would you use them? 
How do you implement custom operators in Swift?
Explain copy-on-write semantics in Swift and how it's used in collections.
5. Testing & Quality:
How do you approach testing in iOS app development? Describe your experience with XCTest and UI testing.
How do you ensure code quality and maintainability in Swift projects? (e.g., code reviews, linting, unit tests) 
6. Problem Solving & Experience:
Describe a challenging technical problem you faced with Swift and how you resolved it. 
Can you talk me through some interesting code you wrote recently? 
How do you stay up to date with changes in Swift and the iOS ecosystem? 
7. Memory Management:
Explain Automatic Reference Counting (ARC) in Swift and how it manages memory.
How do you handle strong reference cycles with closures or delegates?
Explain the difference between strong, weak, and unowned references and when to use each.

Async Await 

Async stands for asynchronous and can be seen as a method attribute, making it clear that a method performs asynchronous work. An example of such a method looks as follows:

            func fetchImages() async throws -> [UIImage] {
                // .. perform data request
            }



      
“Await is awaiting a callback from his buddy async”


        do {
            let images = try await fetchImages()
            print("Fetched \(images.count) images.")
        } catch {
            print("Fetching images failed with error \(error)")
        }

**Retain count**


In Swift, "retain count" is a concept central to Automatic Reference Counting (ARC), Swift's memory management system for reference types (classes).
Here's how it works:
What it is: Every instance of a class in Swift maintains an internal "retain count." This count represents the number of "strong references" pointing to that instance.
How it changes:
When a new instance of a class is created, its retain count starts at 1.
When a strong reference to an instance is created (e.g., assigning it to a new variable or property), its retain count increases.
When a strong reference to an instance is removed (e.g., a variable goes out of scope, or is set to nil), its retain count decreases.
Deallocation: When an instance's retain count drops to zero, it means there are no more strong references holding onto it. At this point, ARC automatically deallocates the instance, freeing up the memory it occupied. The deinit() method of the class is called just before deallocation.
Retain Cycles: A critical issue related to retain counts is a "retain cycle." This occurs when two or more objects hold strong references to each other, creating a closed loop. In such a scenario, even if external references to these objects are removed, their retain counts will never reach zero because they are still strongly referencing each other. This prevents ARC from deallocating them, leading to a memory leak. 
Preventing Retain Cycles: To break retain cycles, you can use "weak" or "unowned" references instead of strong references in specific situations, particularly in closures or delegate patterns where a potential cycle might exist.
Weak references: Do not increase the retain count and are automatically set to nil when the referenced object is deallocated. They are optional (weak var).
Unowned references: Do not increase the retain count and are assumed to always refer to an object that is still in memory. They are non-optional (unowned var) and should only be used when you are certain the referenced object will not be deallocated before the unowned reference.



**View Controller Life cycle**
            First, let’s figure out which order works ViewController and after that dive deeper into each function.

            init()
            loadView()
            viewDidLoad()
            viewWillAppear()
            viewIsAppearing()
            viewWillLayoutSubviews()
            viewDidLayoutSubviews()
            viewDidAppear()
            viewWillTransition()
            viewWillDisappear()
            viewDidDisappear()
            deinit()
