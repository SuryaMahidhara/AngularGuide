+++
title = "Components"
date = "2017-09-05T18:18:17+05:30"
draft = false
+++

Angular2 comes with a new concept called Components which was used to build UI, Write Logic and define data using decorators and class structure.

## Component Selector Naming

        •   Do use dashed-case or kebab-case for naming the element selectors of.

            Example:
            @Component({
                selector: 'date-builder',
                templateUrl: 'date-builder.component.html'
            })

## Components as Elements

        •   Do define components as elements via the selector.

            Example declaration in ts file:
            @Component({
                selector: 'date-builder',
                templateUrl: 'date-builder.component.html'
            })

            Example declaration in html file:
            <date-builder></date-builder>


        •   Do extract templates and styles into a separate file, when more than 3 lines.

            Example declaration in ts file:
            @Component({
                selector: 'date-builder',
                templateUrl: 'date-builder.component.html',
                styleUrls: [datebuilder.component.css]
            })

## Decorate Input and Output Properties Inline

        •   Do use @Input and @Output instead of the inputs and outputs properties of the @Directive and @Component decorators.

            Example declaration in ts file:
            @Component({
                selector: 'date-builder',
                templateUrl: 'date-builder.component.html',
                styleUrls: [datebuilder.component.css]
            })
            export class dateBuilderComponent {
                @Output() change = new EventEmitter<any>();
                @Input() label: string
            }

## Member Sequence

        •   Do place properties up top followed by methods.

        •   Do place private members after public members, alphabetized.

            Example declaration in ts file:
            export class dateBuilderComponent implements OnInit {

                // public properties
                message: string;
                title: string;

                // private properties
                private defaults = {
                    title: '',
                    message: 'I am Indian'
                };
                private dateElement: any;

                // public methods
                activate(message = this.defaults.message, title =  this.defaults.title) {
                    this.title = title;
                    this.message = message;
                    this.show();
                }

                ngOnInit() {
                    this.dateElement = document.getElementById('date-element');
                }

                // private methods
                private showDate() {
                    this.dateElement.style.opacity = 1;                    
                }
            }

## Put Logic in Services

        •	Do limit logic in a component to only that required for the view. All other logic should be delegated to services.

        •	Do move reusable logic to services and keep components simple and focused on their intended purpose.

        •	Why? Logic in a service can more easily be isolated in a unit test, while the calling logic in the component can be easily mocked.


## Don't Prefix Output Properties

        •   Do name events without the prefix on.

        •   Do name event handler methods with the prefix on followed by the event name.

            Example declaration in ts file:
            export class dateBuilderComponent {
                @Output() changeDate = new EventEmitter<any>();
            }

            Example declaration in html file:
            <date-builder (changeDate)="OnChangeDate($event)"></date-builder>

## Put Presentation Logic in the Component Class

        •	Do put presentation logic in the component class, and not in the template.
        
        •	Why? Logic will be contained in one place (the component class) instead of being spread in two places.

            Example declaration in ts file:
            @Component({
                selector: 'events-builder',
                template: `
                    <div>
                        Display list of events
                        <display-event *ngFor="let event of eventsList" [event]="event">
                        </display-event>
                    </div>
                `
            })

            export class eventBuilderComponent {
                eventsList: Event[];
            }





