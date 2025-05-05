# VGL Assignment - OrderDataProcessor
Process the CSV order data by parsing it into structured models to generate an XML file.

OrderDataProcessor Project – Code Structure & Standards: This document outlines the code architecture and best practices followed in the OrderDataProcessor project to ensure clarity, scalability, and maintainability.

Separation of Concerns (SoC) Each responsibility is encapsulated in a dedicated class:
● FileParserService.cs – Reads and parses the CSV file. ● DestinationResolverService.cs – Resolves destination based on supplier code or name. ● XmlGeneratorService.cs – Converts the parsed data into XML format. ● Program.cs – Main entry point; orchestrates parsing, transformation, and output.

Readability and Simplicity (KISS Principle) ● Logic is broken into clear, understandable methods. ● Business rules (e.g., default destinations) are centralized. ● Complexity is minimized through modular functions and early returns.

Don’t Repeat Yourself (DRY Principle) ● Shared logic and models are extracted into reusable components (e.g., Models, Utilities). ● Avoids code duplication in transformation, validation, and data access logic.

SOLID Design Principles ● S – Single Responsibility: Each class handles a single responsibility. ● O – Open/Closed: Easily extendable logic (e.g., new destination rules). ● L – Liskov Substitution: Design supports future interface abstraction. ● I – Interface Segregation: Modular project structure enables interface extraction. ● D – Dependency Inversion: Classes designed for easy DI refactoring (testability).

Models and Data Flow ● HeaderRecord.cs & DetailRecord.cs: Represent structured CSV data. ● FileParserService: Groups headers and details appropriately. ● XmlGeneratorService: Serializes structured data into the required XML format.

Extensibility and Testability ● Stateless methods and mockable services support unit testing. ● Clean project structure enables easy support for new input/output formats. ● Designed for modifiability without impacting existing components.
