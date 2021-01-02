# TypeScript

TypeScript - Open Sourse язык и является надмножеством над JavaScript. Был создан Microsoft.
Присутствует: автокомплит, ES6 фичи, строгая типизация, статический анализ.


### Any

`any` - возвращает поведение как в JavaScript

### Void

В случае если функция ничего не возвращает необходимо есть поставить возвращаемый тип `void`

```typescript
someFunction(param: string): void {
    console.log(param)
}
```

### Optional Parameters

```typescript
someFunction(param: string, optionalParam?: string): void {
    console.log(param, optionalParam)
}
someFunction('test'); // test, undefined
someFunction('test', 'test') // test, test
```

### Default Parameters

```typescript
someFunction(param: string, optionalParam?: string = 'text'): void {
    console.log(param, optionalParam)
}
someFunction('text'); // text, text
someFunction('text', 'anotherText') // text, anotherText
```
### Class

Классы в TypeScript от части было взаимодействовать от C# или Java.
Классы можно наследовать и указывать интерфейс для имплементации.

```typescript
class Base {}
class ChildBase extends Base {}

interface IBase {}
class NewBase implements IBase {}
```

### Access Modifiers

- `public` - доступно везде
- `private` - доступно только внутри класса
- `protected` - доступно только для класса и унаследованных

```typescript
class FooBase {
    public x: number;
    private y: number;
    protected z: number;
}

const foo = new FooBase();
foo.x // OK
foo.y // ERROR: private
foo.z // ERROR: protected

class FooChild extends FooBase {
    constructor(w: string) {
        super();
        this.x; // OK
        this.y; // ERROR: private
        this.z; // OK
    }
}
```

### Interface

TypeScript сравнивает сущности по их типам. Если у нас есть класс и интерфейс с одинаковыми полями, то они равны

```typescript
interface IFoo {
    name: string;
    value: number;
}

class Foo {
    name: string
    value: number;
}

let foo: IFoo;
foo = new Foo(); // OK
```

Наследование:
```typescript
interface IFoo {
    name: string;
    value: number;
}

class Foo implements IFoo {
    name: string;
    value: number;
}
```

### Generic type

Обозначаются `T` - динамический тип данных;

```typescript
function identity<T>(arg: T): T {
    return arg;
}

const resultString: string = identity<string>('text');
const resultNumber: number = identity(100);
```


### Enum

```typescript
enum Cars {
    first = 1,
    second = '2',
    last = first
}
```





