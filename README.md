# ***Application 1 Documentation***

# ***Greeting Application using Blazor***

---

# ***Introduction***

The Greeting Application is a simple Blazor web application developed using ASP.NET Core Blazor.  
This application accepts the user’s name as input and displays a personalized greeting message on the screen.

The main purpose of this application is to demonstrate:

- **One-Way Data Binding**
- **Two-Way Data Binding**
- **Event Handling**
- **Conditional Rendering**
- **Blazor Components**
- **Interactive User Interface**

This application helps beginners understand how data flows between the user interface and backend variables in Blazor.

---

# ***Problem Statement***

Create a Blazor component that accepts a user’s name as input and displays a greeting message using both one-way and two-way data binding.

---

# ***Objective***

The objectives of this application are:

- To understand the concept of data binding in Blazor.
- To implement two-way binding using input controls.
- To display data using one-way binding.
- To learn event handling using button click events.
- To create an interactive user interface.

---

# ***Technologies Used***

| **Technology** | **Purpose** |
|---|---|
| ASP.NET Core Blazor | Web Framework |
| Razor Components | UI Development |
| C# | Backend Logic |
| HTML/CSS | User Interface Design |

---

# ***Component Used***

| **Folder** | **File Name** | **Purpose** |
|---|---|---|
| Pages | GreetingComponent.razor | Main component of Greeting App |

---

# ***Complete Code***

```razor
@page "/greeting"
@rendermode InteractiveServer

<div class="page">

    <div class="box">

        <h1>Greeting App</h1>

        <input type="text"
               @bind="UserName"
               placeholder="Enter your name" />

        <button @onclick="ShowGreeting">
            Submit
        </button>

        @if (ShowMessage)
        {
            <div class="message">
                Hello, @UserName
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-emoji-laughing-fill" viewBox="0 0 16 16">
                    <path d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16M7 6.5c0 .501-.164.396-.415.235C6.42 6.629 6.218 6.5 6 6.5s-.42.13-.585.235C5.164 6.896 5 7 5 6.5 5 5.672 5.448 5 6 5s1 .672 1 1.5m5.331 3a1 1 0 0 1 0 1A5 5 0 0 1 8 13a5 5 0 0 1-4.33-2.5A1 1 0 0 1 4.535 9h6.93a1 1 0 0 1 .866.5m-1.746-2.765C10.42 6.629 10.218 6.5 10 6.5s-.42.13-.585.235C9.164 6.896 9 7 9 6.5c0-.828.448-1.5 1-1.5s1 .672 1 1.5c0 .501-.164.396-.415.235" />
                </svg>
            </div>
        }

    </div>

</div>

@code {

    private string UserName = "";
    private bool ShowMessage = false;

    private void ShowGreeting()
    {
        ShowMessage = true;
    }

}
```

---

# ***Code Explanation***

# ***1. Page Routing***

```razor
@page "/greeting"
```

## **Explanation**

- Defines the URL route of the component.
- The component opens when the user visits:

```text
/greeting
```

---

# ***2. Render Mode***

```razor
@rendermode InteractiveServer
```

## **Explanation**

- Enables interactive server-side rendering.
- Allows real-time user interaction with the component.

---

# ***3. Main Layout Container***

```html
<div class="page">
```

## **Explanation**

- Used as the main container for page content.

---

# ***4. Heading***

```html
<h1>Greeting App</h1>
```

## **Explanation**

- Displays the application title on the webpage.

---

# ***5. Input Field***

```html
<input type="text"
       @bind="UserName"
       placeholder="Enter your name" />
```

## **Explanation**

- Accepts the user’s name as input.
- The `@bind` directive performs two-way data binding.

---

# ***Two-Way Data Binding***

## **Definition**

Two-way data binding means:

- Data moves from UI to variable.
- Data also moves from variable back to UI automatically.

---

## **Implementation in Application**

```razor
@bind="UserName"
```

---

## **Working**

When the user types in the textbox:

```text
Ali
```

The value automatically updates:

```csharp
UserName = "Ali";
```

Similarly, if the variable value changes, the textbox updates automatically.

---

## **Purpose of Two-Way Binding**

- Keeps UI and variable synchronized.
- Reduces manual coding.
- Makes applications interactive.

---

# ***6. Button***

```html
<button @onclick="ShowGreeting">
    Submit
</button>
```

## **Explanation**

- Executes the `ShowGreeting()` method when clicked.

---

# ***Event Handling***

## **Definition**

Event handling means performing an action when an event occurs.

---

## **Event Used**

```razor
@onclick="ShowGreeting"
```

---

## **Functionality**

- Calls the greeting method after button click.
- Displays the greeting message.

---

# ***7. Conditional Rendering***

```razor
@if (ShowMessage)
{
    <div class="message">
        Hello, @UserName
    </div>
}
```

## **Explanation**

- Displays greeting message only when `ShowMessage` becomes true.

---

# ***One-Way Data Binding***

## **Definition**

One-way data binding means:

- Data moves only from variable to UI.
- UI displays the variable value.

---

## **Implementation in Application**

```razor
Hello, @UserName
```

---

## **Working**

The variable value is displayed on the screen:

```text
Hello, Ahmed
```

The UI only reads and displays data from the variable.

---

# ***Difference Between One-Way and Two-Way Data Binding***

| **Feature** | **One-Way Binding** | **Two-Way Binding** |
|---|---|---|
| Data Flow | Variable → UI | UI ↔ Variable |
| Purpose | Display data | Read and update data |
| User Input Update | No | Yes |
| Example in App | `@UserName` | `@bind="UserName"` |

---

# ***Variables Used***

| **Variable** | **Type** | **Purpose** |
|---|---|---|
| UserName | string | Stores user name |
| ShowMessage | bool | Controls visibility of greeting message |

---

# ***Method Explanation***

## **ShowGreeting()**

```csharp
private void ShowGreeting()
{
    ShowMessage = true;
}
```

---

## **Purpose**

- Displays the greeting message after clicking the button.

---

## **Working**

Initially:

```csharp
ShowMessage = false;
```

After button click:

```csharp
ShowMessage = true;
```

The message becomes visible.

---

# ***User Interface Explanation***

The application interface contains:

1. Heading
2. Text Input Field
3. Submit Button
4. Greeting Message Section

---

# ***Application Workflow***

## **Step 1**

User opens the Greeting App page.

---

## **Step 2**

User enters name in textbox.

Example:

```text
Ahmed
```

---

## **Step 3**

Textbox updates variable using two-way binding.

```csharp
UserName = "Ahmed";
```

---

## **Step 4**

User clicks Submit button.

---

## **Step 5**

`ShowGreeting()` method executes.

---

## **Step 6**

Greeting message displays using one-way binding.

```text
Hello, Ahmed 😄
```

---

# ***Output***

# ***Initial Output***

```text
Greeting App

[ Enter your name ]

[ Submit ]
```

---

# ***Final Output***
<img width="1903" height="883" alt="image" src="https://github.com/user-attachments/assets/5e88cc0a-39fa-4986-977e-1fe0b79f7e8b" />
<img width="1892" height="907" alt="image" src="https://github.com/user-attachments/assets/546f421b-96a3-4d3b-8f3d-a50bf23c6682" />



```

---

# ***Concepts Implemented***

| **Concept** | **Description** |
|---|---|
| Blazor Component | Created Razor component |
| Two-Way Binding | Used `@bind` |
| One-Way Binding | Displayed variable using `@UserName` |
| Event Handling | Button click event |
| Conditional Rendering | Used `@if` statement |
| Interactive UI | Dynamic user interaction |

---

# ***Advantages of the Application***

- Simple and easy to understand
- Beginner-friendly
- Demonstrates important Blazor concepts
- Interactive user interface
- Less coding using data binding

---

# ***Conclusion***

The Greeting Application successfully demonstrates both one-way and two-way data binding in Blazor.

- Two-way binding was implemented using:

```razor
@bind="UserName"
```

which synchronizes user input with the variable.

- One-way binding was implemented using:

```razor
@UserName
```

which displays the variable value on the screen.

The application also demonstrates event handling and conditional rendering, making it a useful beginner-level Blazor project for understanding interactive web application development.
