+++
title = "Data Services"
date = 2017-09-06T14:36:31+05:30
draft = false
+++

## Separate Data Calls

        •	Do refactor logic for making data operations and interacting with data to a service.

        •	Do make data services responsible for XHR calls, local storage, stashing in memory, or any other data operations.

                    Why? The component's responsibility is for the presentation and gathering of information for the view. It should not care how it gets the data, just that it knows who to ask for it. Separating the data services moves the logic on how to get it to the data service, and lets the component be simpler and more focused on the view.

                    Why? This makes it easier to test (mock or real) the data calls when testing a component that uses a data service.
                    
                    Why? Data service implementation may have very specific code to handle the data repository. This may include headers, how to talk to the data, or other services such as Http. Separating the logic into a data service encapsulates this logic in a single place hiding the implementation from the outside consumers (perhaps a component), also making it easier to change the implementation.


