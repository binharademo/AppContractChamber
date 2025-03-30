# Contract Chamber - Technical Documentation

## Application Overview

Contract Chamber is a cross-platform mobile application developed to manage, view, and digitally sign contracts. The application allows users to create, share, sign, and manage contracts securely and efficiently, eliminating the need for physical documents and paper signatures.

## Development Period

- **Start Date:** June 2020
- **Completion Date:** June 2020

## Programming Languages

- **C#**: Main language used for application development
- **XAML**: Used for user interface definition

## Main Technologies

- **Xamarin.Forms**: Framework for cross-platform mobile application development
- **Prism**: MVVM framework for Xamarin.Forms that facilitates the development of testable and maintainable applications
- **Microsoft AppCenter**: Used for error monitoring and usage analysis
- **ASP.NET Core 2.0**: Used for the backend (API)
- **Swagger/OpenAPI**: Used for API documentation and client generation

## Supported Platforms

- **Android**
- **iOS**
- **UWP (Universal Windows Platform)**

## Application Architecture

The application follows the MVVM (Model-View-ViewModel) architecture pattern, implemented through the Prism framework, with the following structure:

### Project Structure

1. **AppCamaraDeContratos**: Main Xamarin.Forms project
   - **AppCamaraDeContratos.Android**: Android-specific project
   - **AppCamaraDeContratos.iOS**: iOS-specific project
   - **AppCamaraDeContratos.UWP**: Windows-specific project

2. **AppCamaraPrism**: Alternative project using Prism Framework
   - **AppCamara**: Main implementation with Prism
   - **AppCamara.Shared**: Code shared across platforms
   - **AppCamaraLib.Shared**: Shared libraries

3. **Tests**
   - **XUnitTestModel**: Unit tests for models
   - **XUnitTestProject1**: Additional unit tests

### Application Layers

1. **Models**: Defines business entities
   - Contract
   - Signatory
   - Signers
   - FinalizedContract
   - Invitation

2. **ViewModels**: Implements presentation logic
   - BaseViewModel: Base class that implements INotifyPropertyChanged
   - Specific ViewModels for each functionality

3. **Views**: Defines user interfaces
   - Pages for user registration
   - Pages for contract viewing
   - Pages for contract signing
   - Pages for profile management

4. **Services**: Implements business logic and API communication
   - MockDataStore: Simulated data storage for development
   - AppCenterMethod: Integration with Microsoft AppCenter for monitoring

## Database

The application uses:
- **Local storage**: For temporary data and cache
- **REST API**: For data persistence on the server

There is no evidence of direct use of a local database like SQLite, suggesting that most data is obtained and persisted through the API.

## Persistence Layer

- **REST API**: The application communicates with a backend through a REST API documented with Swagger
- **JSON Serialization**: Uses Newtonsoft.Json for data serialization/deserialization
- **In-memory storage**: For temporary data during application execution

## APIs and Integrations

- **Contracts API**: REST API for contract, user, and signature management
- **ZIP Code API**: Integration for address lookup from ZIP codes
- **Microsoft AppCenter**: For telemetry and error monitoring

## Libraries Used

### Main NuGet Packages:

- **Xamarin.Forms (4.7.0.968)**: Main framework for cross-platform UI
- **Prism.Unity.Forms (7.2.0.1422)**: MVVM implementation and dependency injection
- **Newtonsoft.Json (12.0.3)**: JSON serialization and deserialization
- **Xamarin.Essentials (1.5.3.2)**: Essential APIs for accessing device resources
- **Xam.Plugin.Media (5.0.1)**: Access to camera and photo gallery
- **Plugin.Permissions (6.0.1)**: Permission management
- **Microsoft.AppCenter (3.2.2)**: Telemetry and monitoring
- **Xamarin.Forms.PinchZoomImage (1.0.0)**: Image zoom functionality

## Programming Patterns

- **MVVM (Model-View-ViewModel)**: Main architectural pattern
- **Dependency Injection**: Implemented through Prism.Unity
- **Repository Pattern**: For data access
- **Command Pattern**: For UI command binding
- **Observer Pattern**: Implemented through INotifyPropertyChanged

## Testing Methodology

- **Unit Tests**: Implemented with XUnit
- **Manual Tests**: Evidence of manual testing on iOS devices (documented in DadosTestes.txt)
- **Mock Data**: Use of simulated data for testing

## Main Features

1. **User Authentication and Registration**
   - Login/Logout
   - New user registration
   - Password recovery
   - SMS validation

2. **Contract Management**
   - Creation of new contracts
   - Viewing pending contracts
   - Viewing finalized contracts
   - Adding signatories

3. **Digital Signature**
   - Document viewing for signing
   - Digital contract signing
   - Signatory verification

4. **Profile Management**
   - Viewing and editing personal data
   - Password changing
   - Document and photo upload

5. **Friend Referral**
   - Invitation system for new users

## Code Quality

### Strengths

1. **Structured Organization**: The code follows a clear and organized structure, with proper separation of responsibilities.

2. **Pattern Usage**: Consistent implementation of the MVVM pattern, facilitating maintenance and testability.

3. **Cross-platform**: Efficient development for multiple platforms with code sharing.

4. **API Documentation**: Well-documented API using Swagger/OpenAPI.

5. **Error Handling**: Implementation of error monitoring with AppCenter.

6. **Consistent UI**: Consistent user interface with well-defined visual patterns.

### Areas for Improvement

1. **Simplified Models**: The models found are quite simplified and could be expanded for greater robustness.

2. **Automated Tests**: Although there are test projects, coverage could be expanded.

3. **Code Documentation**: Inline comments and documentation could be more comprehensive.

## Security

- **Token-based Authentication**: Implementation of token-based authentication
- **User Validation**: User validation process via SMS
- **Identity Verification**: Document upload for identity verification

## Conclusion

The Contract Chamber application is a complete solution for digital contract management and signing, developed with modern technologies and following good development practices. The MVVM architecture with Prism provides a solid foundation for maintenance and expansion, while the use of Xamarin.Forms allows reaching multiple platforms with a single code base.

The application demonstrates a good balance between functionality, usability, and security, offering an efficient digital alternative to traditional paper contract signing processes.
