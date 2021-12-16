{
    Tuple to Object
 
 Give an array, transform into an object type and the key/value must in the given array.

For example

```ts
const tuple = ['tesla', 'model 3', 'model X', 'model Y'] as const

type result = TupleToObject<typeof tuple> // expected { tesla: 'tesla', 'model 3': 'model 3', 'model X': 'model X', 'model Y': 'model Y'}
```

배열로 가지고오는 것을 객체 타입에 키와 값으로서 배열의 인덱스를 가져오면된다

 - result
 
 
 ```js
type TupleToObject<T extends string[](any로해도되는데 우선 스트링타입으로하고있어서 명확하게)>
  = { 
 k in T[number] : K
}

 ```
}

{
Readonly

  
interface Todo {
  title: string
  description: string
}

const todo: MyReadonly<Todo> = {
  title: "Hey",
  description: "foobar"
}

todo.title = "Hello" // Error: cannot reassign a readonly property
todo.description = "barFoo" // Error: cannot reassign a readonly property
```

- result

type MyReadonly<T> = {
  readonly [S in keyof T] : T[S]
  }


  // readonly 로 읽기 전용으로 만들고 T 인터페이스에서 받아논 S는 인터페이스의 키중의 하나 : 인터페이스의 키
}

{
Pick


Implement the built-in `Pick<T, K>` generic without using it.

Constructs a type by picking the set of properties `K` from `T`

For example

```ts
interface Todo {
  title: string
  description: string
  completed: boolean
}

type TodoPreview = MyPick<Todo, 'title' | 'completed'>

const todo: TodoPreview = {
    title: 'Clean room',
    completed: false,
}
```

- result

```JS
type MyPick<T, K extends keyof T> = {

  [P in K] : T[P]

}

//T는 인터페이스를 받아온다 K는 T가 받아온 키중의 한개다. 
// p는 T에서 받아온 K중 하나다 결국 [Key]   :   T인터페이스 K키 들중의 P


}
    # 14 번
    {
      14 - First of Array
  -------
  by Anthony Fu (@antfu) #easy #array
  
  ### Question
  
  Implement a generic `First<T>` that takes an Array `T` and returns it's first element's type.
  
  For example
  
  ```ts
  type arr1 = ['a', 'b', 'c']
  type arr2 = [3, 2, 1]
  
  type head1 = First<arr1> // expected to be 'a'
  type head2 = First<arr2> // expected to be 3
  ```
  

    }