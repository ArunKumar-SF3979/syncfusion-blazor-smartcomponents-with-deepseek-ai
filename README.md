# syncfusion-blazor-smartcomponents-with-deepseek-ai
This repository demonstrates the sample for Deepseek AI Integration with Syncfusion Blazor Smartcomponents.

# How to Run the Project

This project demonstrates the integration of **DeepSeek local AI model with Syncfusion Blazor SmartComponents** brings AI-powered automation to text-based applications, enhancing sentence completion, content pasting, and real-time suggestions. 

---
## Prerequisites

Before you begin, ensure you have the following:

1. [**Visual Studio 2022 with the ASP.NET and web development workload**](https://visualstudio.microsoft.com/vs/) installed.
2. **[.NET 8.0 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) or [later](https://dotnet.microsoft.com/en-us/download)**.
3. DeepSeek Model: Installed in your system.
---

## Installing and Setting Up the DeepSeek Model  

To integrate DeepSeek with Syncfusion SmartComponents, you must first install and run the model locally on your system. Follow these steps to get started:  

### Step 1: Install Ollama  
Download and install Ollama from [Ollama's official website](https://ollama.com) based on your operating system.  

### Step 2: Install the DeepSeek Model  
After installing Ollama, open a command prompt or terminal and run the following command to install and start the DeepSeek model:  

```sh
ollama run <model-name>
```

Replace `<model-name>` with the specific DeepSeek model you want to use. For example:  

```sh
ollama run deepseek:7b
```

Once the model is running, it will be hosted locally and can be used within Syncfusion SmartComponents for AI-powered text assistance.  

## Steps to Run the Project

### 1. Clone the Repository
Clone the repository to your local machine:
```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Install Required Dependencies
Make sure all required NuGet packages are installed. Use the following commands if necessary:
```bash
dotnet restore
```

---

### 3. Configure the Deepseek ai model in program.cs

To configure the AI service, add the following settings to the `~/Program.cs` file in your Blazor application:  

```csharp
builder.Services.AddSyncfusionSmartComponents()
    .ConfigureCredentials(new AIServiceCredentials 
    { 
        SelfHosted = true, 
        Endpoint = new Uri("Your local endpoint"), 
        DeploymentName = "your model name" 
    })
    .InjectOpenAIInference();
```

- Set `SelfHosted` to `true`.  
- Provide the `Endpoint` URL where the model is hosted (e.g., `http://localhost:11434`).  

## Installing and Running the DeepSeek Model  
Before proceeding, ensure the DeepSeek model is installed and running locally. You can install the model using the following command:  

```sh
ollama run <model-name>
```

Replace `<model-name>` with the specific DeepSeek model you want to use. For example:  

```sh
ollama run deepseek-r1:1.5b
```

Once the model is running, set the `DeploymentName` to match the installed model, such as:  

- `deepseek-r1:1.5b`  
- `deepseek-r1:7b`  
- `mistral:7b`  

This setup enables Syncfusion SmartComponents to leverage AI-powered text assistance using the locally hosted DeepSeek model.  

---

### 4. Build and Run the Project
Run the following command to build and start the application:
```bash
dotnet run
```

---

### 5. Access the Application
Once the application starts, open your browser and navigate to the provided URL.


