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


