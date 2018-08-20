# Contains: 

* `Login` - A set of credentials used to authenticate a user. On this project, it consists of a username and password.
* `Register` - the act or process of entering information about something to the database for the purpose of information authentication.
* `Request Table` - Build the documentation site.


## Login: 
* Login is using react JS front end (look at client/src/pages/login/index.js). Also using redux to change the state after the login is success (the state is changed when it hits client/src/pages/login/model.js line 15). 
```
client/src/pages/login/index.js
```
It connects to the back end with axios, which is called by client/src/pages/login/service.js on its post URL. The back end can be seen on server.js page (line 240). 

* **Flow**: 
    1. Starting on index.js file, when the button Sign In is clicked, it will go to function handleOK
    2. The function handleOK will send the data to models.js in the same folder with namespace login and method name login.
    3. In model.js line 11, data will contains boolean true or false by doing method login on service.js.
    4. The method login on page service.js will return request to post to url userLogin which can be found on ../utils/config.js
    5. url userLogin will get its method from client/mock/user.js file line 94. 
    6. The url will hit the back end after called by axios. If success, it will assign boolean success to const data back in client/src/pages/login/model.js
    7. If success, the program will call app/query in ../../models/app.js (line 68). The program will also call query function from services/app that will post URL query in file services/app.js. The function query will get url /user in client/mock/user.js.
    8. If the password and username match, it will change the reducer's state in app.js (line 91). The reducer's state will be base on the value that the user's input.
    9. After that, it will return to client/src/pages/login/model.js and it will push the page before login, or if it is the first time login, you'll be directed to dashboard.



* **Redux Concept from [https://redux.js.org/basics/reducers](https://redux.js.org/basics/reducers):**

Redux have 3 components: Actions, Reducers, and Store. 

1. **Action** is a plain JavaScript object that describes what happened, for example: 
    ```
    const ADD_TODO = 'ADD_TODO'
    { type: 'ADD_TODO', text: 'Go to swimming pool' }
    ```
Every change is described as an action lets us have a clear understanding of what’s going on in the app. If something changed, we know why it changed. 
Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using store.dispatch()

**Action Creators**
Action creators are functions that create actions. For example: 
```
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
To initiate a dispatch(An action creator is a function that fires off an action), pass the result to the dispatch() function:
```
dispatch(addTodo(swimming))
```


2. **Reducer** is a function that takes state and action as arguments, and returns the next state of the app. Reducers are just pure functions that take the previous state and an action, and return the next state. For example: 
    ```
    function todos(state = [], action) {
        switch (action.type) {
            case 'ADD_TODO':
            return state.concat([{ text: action.text, completed: false }])
            case 'TOGGLE_TODO':
            return state.map(
                (todo, index) =>
                action.index === index
                    ? { text: todo.text, completed: !todo.completed }
                    : todo
            )
            default:
            return state
        }
    }

    ```

* Difference Redux concept from this template: 


* How to Change parameters on Login Form


## Register:
* Register is using react JS front end (look at client/src/pages/register/index.js). 
```
class Register extends React.Component {
  state = {
    confirmDirty: false,
    autoCompleteResult: [],
  } 

```

It uses ANTD form for its template, so we can use the method provided by ANTD form [here](https://ant.design/components/form/)



