+++
title = "Directives"
date = "2017-09-05T18:20:17+05:30"
draft = false
+++

## Use Directives to Enhance an Existing Element

        •	Do use attribute directives when you have presentation logic without a template.

                Why? Attributes directives don't have an associated template.
                Why? An element may have more than one attribute directive applied.

                Example in directive ts file:
                @Directive({
                    selector: '[tohHighlight]'
                })

                export class HighlightDirective {

                    @HostListener('mouseover') onMouseEnter() {
                        // do highlight work
                    }
                }

## Use HostListener and HostBinding Class Decorators

        •	Consider preferring the @HostListener and @HostBinding to the host property of the @Directive and @Component decorators.
        
        •	Do be consistent in your choice.

                Why? The property associated with @HostBinding or the method associated with @HostListener can be modified only in a single place - in the directive's class. If you use the host metadata property, you must modify both the property declaration inside the controller, and the metadata associated with the directive.

                Example:

                app/shared/validator.directive.ts -

                    import { Directive, HostBinding, HostListener } from '@angular/core';

                    @Directive({
                        selector: '[tohValidator]'
                    })
                    export class ValidatorDirective {

                        @HostBinding('attr.role') role = 'button';
                        @HostListener('mouseenter') onMouseEnter() {
                            // do work
                        }
                    }

        •	Compare with the less preferred host metadata alternative.

                Why? The host metadata is only one term to remember and doesn't require extra ES imports.

                Example:

                app/shared/validator2.directive.ts

                    import { Directive } from '@angular/core';
 
                    @Directive({
                        selector: '[tohValidator2]',
                        host: {
                            '[attr.role]': 'role',
                            '(mouseenter)': 'onMouseEnter()'
                        }
                    })

                    export class Validator2Directive {

                        role = 'button';
                        onMouseEnter() {
                            // do work
                        }
                    }





