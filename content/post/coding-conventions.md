+++
title = "Coding Conventions"
date = 2017-09-06T14:35:42+05:30
draft = false
+++

Have consistent set of coding, naming, and whitespace conventions.

## Classes

        •	Do use upper camel case when naming classes.

            Example:
            export class DateProviderService {
                constructor () { }
            }

## Constants

        •	Do declare variables with const if their values should not change during the application lifetime.

        •	Consider spelling const variables in lower camel case.

        •	Do tolerate existing const variables that are spelled in UPPER_SNAKE_CASE.

            Example:
            export const mockHeroes = ['Sam', 'Jill'];
            export const heroesUrl = 'api/heroes';

## Interfaces

        •	Do name an interface using upper camel case.

        •	Consider naming an interface without an I prefix. ( TypeScript guidelines discourage the "I" prefix.)

        •	Consider using a class instead of an interface.

            Example:
            import { Injectable } from '@angular/core';

            import { Hero } from './hero.model';

            @Injectable()
            export class HeroCollectorService {
            hero: Hero;

            constructor() { }
            }

## Properties and Methods

        •	Do use lower camel case to name properties and methods.

        •	Avoid prefixing private properties and methods with an underscore.

## Import Line Spacing

        •	Consider leaving one empty line between third party imports and application imports.

        •	Consider listing import lines alphabetized by the module.

        •	Consider listing destructured imported assets alphabetically.

            Example:
            import { Injectable } from '@angular/core';
            import { Http }       from '@angular/http';

            import { Hero } from './hero.model';
            import { ExceptionService, SpinnerService, ToastService } from '../../core';








