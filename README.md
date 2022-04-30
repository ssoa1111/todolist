# REACT로 만드는 Todolist

## useState()
useState()는 데이터 값이 자주 변하는 곳에 상태 관리를 할 수 있게 합니다.
```javascript
const [todos, setTodos] = useState()
```

## useRef()
useRef()는 값이 변경되어도 렌더링 되지 않습니다.
```javascript
const nextId = useRef(4);
```

## useCallback()
useCallback()은 의존성 배열에 따라 렌더링 됩니다.
```javascript
const onInsert = useCallback((text)=>{
    const todo = {
      id : nextId.current,
      text,
      checked : false
    };
    setTodos(todos.concat(todo));
    nextId.current += 1;
  });
```

## filter()
filter()는 배열의 내용이 참인 것만 거를 수 있습니다,
```javascript
setTodos(todos.filter((todo)=>todo.id !== id));
```

## map()
map()는 forEach()같이 배열을 조회할 수 있지만 새로운 배열을 리턴합니다.
```javascript
setTodos(todos.map((todo)=>
      todo.id === id ? {...todo, checked : !todo.checked} : todo,
    ))
```


### 깃 페이지 만드는 순서
1. 터미널 yarn add gh-pages
2. package.json 파일에서 homepage 추가
```javascript
"homepage": "https://ssoa1111.github.io/todolist"
```
3. git push 완료하기
4. 터미널에서 yarn deploy