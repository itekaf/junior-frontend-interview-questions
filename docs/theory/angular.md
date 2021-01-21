# Angular 

Angular - это 

## Background 

- [Lifecycle](#lifecycle)
- [Data Binding](#data-binding)
- [RxJS](#rxjs)

### Lifecycle

Порядок выполнения "хуков" сохранен

- `NgOnChanges` - срабатывает каждый раз когда меняется `Input` проперти когда мы передаем в нашу компоненту. Вызывается перед `NgOnInit`
- `NgOnInit` - срабатывает один раз при после `NgOnChanges` и иинициализует какие-то данные, т.к. работает с данными (вызывает сервисы).
- `NgDocheck` - в отличии от `NgOnChnages` он отрабатывает при каждом прогоне `NgOnAction`??? Например: есть форма, при каждом измении каждого элемента будет вызывать `NgDoCheck` - это доргая операция и имеет смысл при кастомных валидациях
- `NgAfterContentInit` -
- `NgAfterContentChecked` -
- `NgAfterViewInit` -
- `NgAfterViewChecked` -
- `NgOnDestroy` -  используется перед тем как Ангуляр уничтожит компоненту. Используется для уничтожения всяких евентов и т.д. Чтобы обезопасить себя на `memory leaks`.

### Data binding

- `{{property}}` - Интерполяция - example: `<p>{{message}}</p>`;
- `[]="property"` - Property Binding - example: `<h2 [textContent]="message"><h2>`
- `()="method()"` - Event Binding - example: `<button (click)="sayHello()">Say hello</button>`;
- `[(ngModel)]="property"` - Two Way Binding
    - example: `<input [(ngModel)]="username"`;
    - bannas in the box
    - It's = `[ngModel]="username" (ngModelChange)="...."`

### RxJS

