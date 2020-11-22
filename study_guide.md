Ruby Assessment 2 Learning Objectives

Below are the learning objectives that Ruby Assessment 2 will test.
Object Oriented Programming

    Given a set of classes, some inheriting from others, correctly identify what methods an instance of each class has access to
    Given a parent and child class, correctly use the super method, passing only the necessary arguments, in the child class initialize method to handle shared initialization logic
    Implement a class inheritance chain using proper Ruby syntax

    Explain the difference between public, private, and protected methods

        + Public Methods
            - are accessible from outside the class (ex: class_name.some_method)
            - Public methods can be called by anyone---there is no access control.
            - Methods are public by default

        + Private Methods
            - Not accessible from outside the class. (ex: class_name.some_method does not execute)
            - Because you cannot specify an object when using them, private methods can be called only in the defining class
            - Private methods cannot be called with an explicit receiver. (ex: calling self.some_method inside the class DOES NOT exectute )
            - Exception*** explicit receiver rule: explicit receiver can be used on setter methods only.

        + Protected Methods
            - Protected methods can be invoked only by objects of the defining class and its subclasses. Access is kept within the family.
            - protected methods can be called with an explicit receiver, so long as the caller is of the same class. (ex: calling self.some_method inside of the class DOES execute)

    Explain the difference between inheriting from a class and including a module
        +

Big O Analysis

    Explain what "Big O" is and why we utilize it
        + Big-O notation is a relative representation of the complexity of an algorithm
        +   - It measures the worst-case-scenario runtime
        +   - It is concerned with measuring algorithmic efficiency in large scale, particularly, as variable n approaches infinity.
        +   - Utilizes asymtotic analysis.
        +   - Ignores constants when calculating
        +   - Defaults to "most dominant trait" ; "only as fast as the bottleneck"

        + Big-O Classifications:
        +   - O(1)          => Constant runtime. Input size has no effect on performance.
        +   - O(log_n)      => Logarithmic: The larger n gets, the less impact it has on time; "inverse of exponential growth"; ex: Binary Search (b-search)
        +   - O(n)          => Linear: bigO == size of input, n; ex: iterating through an array one time.
        +   - O(n * log_n)  => Loglinear: combined result of a method that has O(n)*O(log_n) complexity. ex: Merge Sort, and Quick Sort. I pneumonic this by thinking of methods that utilize a logarithmic property (n/2 in a loop) but still require iteration to organize.

        +   - O(n^2)        => Quadratic: n * n iterative passes; ex: nested loops, bubble sort
        +   - O(n^k)        => Polynomial: Same as quadratic but k = number of times iterating through;
        +   - O(k^n)        => Exponential: k to the power of n times; ex: subsets
        +   - O(n!)         => Factorial: Anything factorial...? : ex: permutations.



    Given an implementation of an algorithm, determine its Big O time complexity
    Given a description of a problem (such as anagrams or two_sum), implement a solution that runs in linear time.

Data Structures

    Describe what LIFO and FIFO are and how they relate to the Stack and Queue ADTs, respectively


    Describe the difference between an Abstract Data Type (ADT) and Data Structure
        Abstract Data Structure
        +   - Conceptual description of a process for storing/retrieving data
        +   - ADS is programming language agnostic. Doesn't refer to the specific code required to implement.
        +   - Describes the API (Aplication Programming Interface) for data retrieval
        +   - Examples
        +   +   - Stack - last in first out "LIFO"
        +   +   - Queue - First in first out "FIFO"
        +   +   - Tree - Parent child relationship
        +   +   - Maps/Set/Array/

        Data structure is the implementation of an ADS in code.


    Given an ADT, identify what underlying data structures native to Ruby could be used to implement the ADT
    Given a description of an algorithm, identify what ADTs would be useful in implementing a solution
    Implement a Stack data structure
    Implement a Queue data structure

CSS

    Given a pre-filled HTML skeleton, write CSS selectors to add specific styles to specific html tags, classes, and ids
    Given an HTML skeleton, utilize the > selector in CSS to select all p elements that are children of the element with id index and give them all a font-size of 18px and background color of red (or any other basic CSS properties)
    Use the :last-child selector to give the last item in an ordered list a color of green
    Use the + selector to select the first sibling element of the h1 tag and give it a 1px solid black border

                  <-- examples of css selectors -->

        body  { some_property: value; }              => use an HTML element <tag_name> to select all elements of that type. ths example uses <body></body> tag.
        #id_tag  { some_property: value; }           => # is used to select an "id" type tag.
        .class_tag { some_property: value; }         => . is used to select a "class" type tag.
        ol :first-child { some_property: value; }    => selects first child of a parent tag
        ol :last-child { some_property: value;  }    => selects last child of a parent tag
        ol :nth-child(even){    '''             }    => selects certain children of a parent tag
        input[type="submit"]:hover {    '''     }    => (selects certain attributes of tags

        the "+" selector will select the first sibling element:
            => example: div + p 	Selects all <p> elements that are placed immediately after <div> elements

        the ">" selector in CSS to select all p elements that are children of the element
            => example: div > p 	Selects all <p> elements where the parent is a <div> element

        the :last-child
            => p:last-child 	Selects every <p> element that is the last child of its parent


    ex: CSS style-sheet from practice exam.

    i {
        font-size: 15px;
    }
    # list-header {
        background-color: blue;
    }

    .ruby {
        color: red;
    }
    li > span {
        background-color: yellow;
    }

    li span {
        background-color: yellow;
    }

Test Driven Development/RSpec

    Describe at least 3 primary motivations for having automated test suites
    + Removes user error
    + Make sure code does what it is expected to do
    + write tests for any public methods
    + makes refactoring easier as sections of code can be tested independently of the whole.

    Explain the difference between Unit Tests and Integration Tests
        +  unit test tests as small a portion of code as possible. Utilizes doubling(?!?) to remove potential outside influence affecting results.
        +  integration test: Tests how disparate pieces of a program interact with each other.
        +  end to end test. Not automated. final piece of any developement.


    Describe the basic workflow of Test Driven Development
        + write test, write code, refactor
            - write a test to define the purpose of the code. Ensure the test fails to remove potential for false positives when running with the intended code.
            - write code that satisfies the test, limiting to single or very small tests at any given time.
            - Refactor/optimize after tests pass. Continue running tests to ensure any changes do not affect the intended outcome.

    Explain the use case of a double or mock when writing unit tests
        + A test double is a fake, or mock, object that we can create in testing environment to control for desired outcomes of specific code that might depend on other bits of code.
            - Rather than utilize some dependent code/method to pass in data, creating a double that can stand in place of any outside required code helps to control the immediate code being tested in isolation.


    Describe the difference between RSpec's describe and context and when you should use each
        + "it" is RSpec's most basic test unit. All of your actual individual tests will go inside of an it block
        + A"describe" is RSpec's unit of testing organization. A "describe" block with "do-end" wraps a test. A string wrapped in quotations is used to describe a method or object on which the tests that follow will be called. Within a "describe" block, "it" blocks are used to describe/produce a particular test and the expected behavior.
        + A "context" block is functionally the same as "describe" but it is intended to be used to describe as a means of organizing a series of tests that check behaviour under some paticular set of circumstances.

    Given an assertion, correctly set up an it block that uses expect to test for the assertion

        describe "#hello_world" do
            it "returns 'Hello, World!'" do
                expect(hello_world).to eq("Hello, World!")
            end
        end
