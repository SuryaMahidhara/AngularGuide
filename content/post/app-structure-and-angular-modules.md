+++
title = "App Structure And Angular Modules"
date = 2017-09-06T14:36:11+05:30
draft = false
+++

## Flat

        •	Do keep a flat folder structure as long as possible.

        •	Consider creating sub-folders when a folder reaches seven or more files.

## Overall Structural Guidelines

        •	Put all of the app's code in a folder named app.

        •	Consider creating a folder for a component when is has multiple accompanying files (.ts, .html, .css and .spec).

## App Root Modules

        •	Do create an Angular module at the root of the application.

        •	Every app requires at least one Angular module.

        •	Consider naming the root module app.module.ts.

            Example:
            import { NgModule }      from '@angular/core';
            import { BrowserModule } from '@angular/platform-browser';
            
            import { AppComponent }    from './app.component';
            import { HeroesComponent } from './heroes/heroes.component';
            
            @NgModule({
            imports: [
                BrowserModule,
            ],
            declarations: [
                AppComponent,
                HeroesComponent
            ],
            exports: [ AppComponent ],
            entryComponents: [ AppComponent ]
            })
            export class AppModule {}

## Feature Modules

        •	Do create an Angular module for all distinct features in an application (e.g. Heroes feature).

        •	Do place the feature module in the same named folder as the feature area (.e.g app/heroes).

        •	Do name the feature module file reflecting the name of the feature area and folder (e.g. app/heroes/heroes.module.ts)

        •	Do name the feature module symbol reflecting the name of the feature area, folder, and file (e.g.app/heroes/heroes.module.ts defines HeroesModule).

## Shared Feature Module

        •	Do create a feature module named SharedModule in a shared folder (e.g. app/shared/shared.module.ts definesSharedModule).

        •	Do put common components, directives and pipes that will be used throughout the application by other feature modules in the SharedModule

## Core Feature Module

        •	Do create a feature module named CoreModule in a core folder (e.g. app/core/core.module.ts defines CoreModule).

        •	Do put a singleton service whose instance wil be shared throughout the application in the CoreModule (e.g.ExceptionService and LoggerService).

## Prevent Reimport of Core Module

        •	Only the root AppModule should import the CoreModule.

        •	Do guard against reimporting of CoreModule and fail fast by adding guard logic.

## Lazy Loaded Folders

        •	A distinct application feature or workflow may be lazy loaded or loaded on demand rather than when the application starts.

        •	Do put the contents of lazy loaded features in a lazy loaded folder. A typical lazy loaded folder contains a routing component, its child components, and their related assets and modules.

## Never Directly Import Lazy Loaded Folders

        •	Avoid allowing modules in sibling and parent folders to directly import a module in a lazy loaded feature.

        •	Why? Directly importing and using a module will load it immediately when the intention is to load it on demand.
        



        






