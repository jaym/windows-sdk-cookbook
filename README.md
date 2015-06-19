# Windows SDK Cookbook

## Description
This cookbook installs the Windows 8.1 SDK. More information about the SDK
can be found at https://msdn.microsoft.com/en-us/windows/desktop/bg162891.aspx

## Usage

This cookbook provides a resource that can be used to install and uninstall
features provided with the Windows SDK.

### windows_sdk_feature Resource

#### Actions
- `:install`: Default. Install the given feature(s)
- `:uninstall`: Uninstall the given feature(s)

#### Attribute Parameters
- :features: Name Attribute. A feature(Symbol), an Array of features, or `:all`

  Valid features:
  - `:windows_software_development_kit`: The Microsoft Windows Software 
  Development Kit for Windows 8.1
  - `:windows_performance_kit`: Windows Performance Toolkit
  - `:debugging_tools`: Debugging Tools for Windows
  - `:application_verifier`: Application Verifier for Windows
  - `:windows_app_certification_kit`: Windows App Certification Kit
  - `:msi_tools`: MSI Tools
  - `:netfx_software_development_kit`: .Net Frame 4.5 Software Development Kit

#### Examples

Install all features:

```ruby
windows_sdk_feature :all
```

Install only the debugging tools and MSI tools

```ruby
windows_sdk_feature [:debugging_tools, :msi_tools]
```

Uninstall the MSI tools

```ruby
windows_sdk_feature :msi_tools do
  action :uninstall
end
```

