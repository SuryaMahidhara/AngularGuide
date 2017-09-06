+++
title = "Services"
date = "2017-09-05T18:23:17+05:30"
draft = false
+++

## Services are Singletons within an Injector

        •	Do use services as singletons within the same injector. Use them for sharing data and functionality.

                Why? Services are ideal for sharing methods across a feature area or an app.
                Why? Services are ideal for sharing stateful in-memory data.

                Example:
                export class HeroService {
                    constructor(private http: Http) { }

                    getHeroes() {
                        return this.http.get('api/heroes')
                        .map((response: Response) => <Hero[]>response.json().data);
                    }
                }

## Single Responsibility

        •	Do create services with a single responsibility that is encapsulated by its context.

        •	Do create a new service once the service begins to exceed that singular purpose.

                Why? When a service has multiple responsibilities, it becomes difficult to test.
                Why? When a service has multiple responsibilities, every component or service that injects it now carries the weight of them all.

## Providing a Service

        •	Do provide services to the Angular injector at the top-most component where they will be shared.

                Why? The Angular injector is hierarchical.
                Why? When providing the service to a top level component, that instance is shared and available to all child components of that top level component.
                Why? This is ideal when a service is sharing methods or state.
                Why? This is not ideal when two different components need different instances of a service. In this scenario it would be better to provide the service at the component level that needs the new and separate instance.

                Example:
                import { Component } from '@angular/core';
 
                import { HeroService } from './heroes';
                
                @Component({
                selector: 'toh-app',
                template: `
                    <toh-heroes></toh-heroes>
                    `,
                providers: [HeroService]
                })
                export class AppComponent {}

## Use the @Injectable() Class Decorator

        •	Do use the @Injectable class decorator instead of the @Inject parameter decorator when using types as tokens for the dependencies of a service.

                Why? The Angular DI mechanism resolves all dependencies of services based on their types declared with the services' constructors.
                Why? When a service accepts only dependencies associated with type tokens, the @Injectable() syntax is much less verbose compared to using@Inject() on each individual constructor parameter.

                Example:
                @Injectable()
                export class HeroArena {
                    constructor(
                        private heroService: HeroService,
                        private http: Http) {}
                }

