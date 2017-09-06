+++
title = "Naming"
date = 2017-09-06T14:34:56+05:30
draft = false
+++

Naming conventions are hugely important to maintainability and readability

## General Naming Guidelines

        •	Do use consistent names for all symbols.

        •	Do follow a pattern that describes the symbol's feature then its type. The recommended pattern is feature.type.ts.

## Separate File Names with Dots and Dashes

        •	Do use dashes to separate words in the descriptive name.

        •	Do use dots to separate the descriptive name from the type.
        
        •	Do use consistent type names for all components following a pattern that describes the component's feature then its type. A recommended pattern is feature.type.ts.
        
        •	Do use conventional type names including .service, .component, .pipe, .module, .directive. Invent additional type names if you must but take care not to create too many.

## Symbols and File Names

        •	Do use consistent names for all assets named after what they represent.

        •	Do use upper camel case for class names. Match the name of the symbol to the name of the file.

        •	Do append the symbol name with the conventional suffix for a thing of that type (e.g., Component, Directive, Module, Pipe, Service).

        •	Do give the filename the conventional suffix for a file of that type (e.g., .component.ts, .directive.ts, .module.ts, .pipe.ts,.service.ts).

            Example1:
            @component({....})             
            export class AppComponent { }

            For above example file name should be app.component.ts

            Example2:
            @component({....})             
            export class DateGeneratorComponent { }

            For above example file name should be date-generator.component.ts

## Service Names

        •	Do use consistent names for all services named after their feature.
        
        •	Do use upper camel case for services.

        •	Do suffix services with Service when it is not clear what they are (e.g. when they are nouns).

            Example:
            @Injectable()
            export class DateService { }

            For above example file name should be date.service.ts

## Bootstrapping

        •	Do put bootstrapping and platform logic for the app in a file named main.ts.

        •	Do include error handling in the bootstrapping logic.

        •	Avoid putting app logic in the main.ts. Instead consider placing it in a component or service.

            Example:
            import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
            import { AppModule }              from '.app/app.module';

            platformBrowserDynamic().bootstrapModule(AppModule)
                .then(success => console.log(`Bootstrap success`))
                .catch(err => console.error(err));
            
## Directive Selectors

        •	Do Use lower camel case for naming the selectors of directives.

## Custom Prefix for Components

        •	Do use a hyphenated, lowercase element selector value (e.g. admin-users).

        •	Do use a custom prefix for a component selector. For example, the prefix toh represents from Tour of Heroes and the prefix admin represents an admin feature area.

        •	Do use a prefix that identifies the feature area or the app itself.

            Example:
            @component({
                selector: 'toh-hero'
            })
            export class HeroComponent {}

## Custom Prefix for Directives

        •	Do use a custom prefix for the selector of directives (e.g, the prefix toh from Tour of Heroes).

        •	Do spell non-element selectors in lower camel case unless the selector is meant to match a native HTML attribute.

            Example:
            @Directive({
                selector: '[validate]'
            })
            export class ValidateDirective {}

## Pipe Names

        •	Do use consistent names for all pipes, named after their feature.

            Example:
            @Pipe({ name: 'convertToString' })
            export class ConvertToStringPipe implements PipeTransform { }

            The file name for above example will be convert-to-string.pipe.ts

## Unit Test File Names

        •	Do name test specification files the same as the component they test.

        •	Do name test specification files with a suffix of .spec.

            Example:
            Components - heroes.component.spec.ts

## Angular NgModule Names

        •	Do append the symbol name with the suffix Module.

        •	Do give the file name the .module.ts extension.

        •	Do name the module after the feature and folder it resides in.

        •	Do suffix a RoutingModule class name with RoutingModule.

        •	Do end the filename of a RoutingModule with -routing.module.ts.

            Example:
            @NgModule({ ... })
            export class AppModule { }

            The file name for above example will be app.module.ts