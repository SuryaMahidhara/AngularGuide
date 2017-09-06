+++
title = "Single Responsibility"
date = 2017-09-06T14:34:25+05:30
draft = false
+++

Apply the Single Responsibility Principle to all components, services, and other symbols. This helps make the app cleaner, easier to read and maintain, and more testable.

## Rule of One

        •	Do define one thing (e.g. service or component) per file.

        •	Consider limiting files to 400 lines of code.
            o	Why? One component per file makes it far easier to read, maintain, and avoid collisions with teams in source control.

            o	Why? One component per file avoids hidden bugs that often arise when combining components in a file where they may share variables, create unwanted closures, or unwanted coupling with dependencies.

            o	Why? A single component can be the default export for its file which facilitates lazy loading with the Router.

## Small Functions

        •	Do define small functions.
        
        •	Consider limiting to no more than 75 lines.




