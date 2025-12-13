# Soenneker.Extensions.ServiceCollection.ApplicationInsights

![GitHub](https://img.shields.io/github/license/Navya-Gannavarapu/soenneker.extensions.servicecollection.applicationinsights)
![Release](https://img.shields.io/github/v/release/Navya-Gannavarapu/soenneker.extensions.servicecollection.applicationinsights)

Welcome to **Soenneker.Extensions.ServiceCollection.ApplicationInsights**! This repository offers a collection of useful `IServiceCollection` extension methods that simplify the integration of Application Insights into your .NET applications. 

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Available Extensions](#available-extensions)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- **Simplified Integration**: Easily add Application Insights to your .NET applications.
- **Flexible Configuration**: Customize your telemetry settings with minimal effort.
- **Extensible**: Extend the functionality as per your application's needs.
- **Support for JWT**: Includes methods for JWT authentication and telemetry.

## Installation

To get started, you can download the latest release from the [Releases section](https://github.com/Navya-Gannavarapu/soenneker.extensions.servicecollection.applicationinsights/releases). Make sure to download the appropriate package and execute it in your project.

### NuGet Package

You can also install the package via NuGet. Run the following command in your Package Manager Console:

```bash
Install-Package Soenneker.Extensions.ServiceCollection.ApplicationInsights
```

## Usage

Integrating Application Insights into your application is straightforward. Here’s a simple example of how to use the extension methods provided in this repository.

### Step 1: Configure Services

In your `Startup.cs` or wherever you configure your services, add the following:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddApplicationInsightsTelemetry(Configuration["ApplicationInsights:InstrumentationKey"]);
    
    // Additional services can be added here
}
```

### Step 2: Using the Extensions

You can utilize the provided extension methods to add more telemetry features. Here’s an example:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddApplicationInsightsTelemetry(Configuration["ApplicationInsights:InstrumentationKey"]);
    
    // Adding custom telemetry
    services.AddTelemetryServices();
}
```

### Step 3: Custom Telemetry

To send custom telemetry data, you can create a service that uses the telemetry client:

```csharp
public class CustomTelemetryService
{
    private readonly TelemetryClient _telemetryClient;

    public CustomTelemetryService(TelemetryClient telemetryClient)
    {
        _telemetryClient = telemetryClient;
    }

    public void TrackEvent(string eventName)
    {
        _telemetryClient.TrackEvent(eventName);
    }
}
```

## Available Extensions

Here are some of the key extensions available in this repository:

1. **AddTelemetryServices**: Adds essential telemetry services to the service collection.
2. **AddJwtTelemetry**: Configures telemetry for JWT authentication.
3. **AddCustomTelemetry**: Allows you to send custom telemetry data easily.

## Contributing

We welcome contributions! If you want to improve this project, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Write tests for your changes.
5. Submit a pull request.

For detailed guidelines, please check the `CONTRIBUTING.md` file in the repository.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/Navya-Gannavarapu/soenneker.extensions.servicecollection.applicationinsights/blob/main/LICENSE) file for details.

## Contact

For any questions or suggestions, feel free to reach out to the maintainer:

- **Name**: Navya Gannavarapu
- **Email**: navya@example.com
- **GitHub**: [Navya-Gannavarapu](https://github.com/Navya-Gannavarapu)

---

Thank you for checking out **Soenneker.Extensions.ServiceCollection.ApplicationInsights**! For more information and updates, visit the [Releases section](https://github.com/Navya-Gannavarapu/soenneker.extensions.servicecollection.applicationinsights/releases).