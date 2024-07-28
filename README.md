# Collapsible Nav Menu for Blazor

This project is based on a solution originally discussed in the Microsoft Tech Community by Gavin Williams. The initial concept was shared in February 2023 ([Here](https://techcommunity.microsoft.com/t5/web-development/convert-the-standard-blazor-navigation-menu-to-a-collapsible/m-p/3753268)).

The original implementation didn't work out of the box for .NET 8 Blazor applications, but with contributions from various community members, the project has been refined and made fully functional. I've made this repo for ease and expanded to fix an issue with the nav collapsing when the width goes to a determind width.

### Features
- Fully collapsible navigation menu.
- Supports expanding and collapsing without graphical issues.
- Uses Bootstrap icons for UI elements.
- Works seamlessly in Blazor Server applications.
- Demonstrates usage in both Blazor Server and Blazor WebAssembly projects.

### Getting Started
To integrate the collapsible icon menu into your project, follow these steps:
1. Copy the `NavMenu.razor`, `NavMenu.razor.css` & `MainLayout.razor` into your project.
2. Either take a copy of the `App.razor` or take a copy of this script into you project

    ```
    <script>
        window.setResizeCallback = (dotNetHelper) => {
            const resizeCallback = () => {
                const isBelowThreshold = window.innerWidth < 642;
                dotNetHelper.invokeMethodAsync('OnResize', isBelowThreshold);
            };

            window.addEventListener('resize', resizeCallback);
            resizeCallback();
        };
    </script>
    ```
3. Adjust the sizing and behavior in `App.razor` if needed.

### Acknowledgments
- Gavin Williams ([GitHub Profile](https://github.com/DrGav)) | ([MSFT Tech Community Profile](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/1750639))
