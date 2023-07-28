[#react]
[Roadmap](https://roadmap.sh/react)

- state
	- React batches state updates (event handlers, lifecycle methods, and non-React-controlled: promises, setTimeout)
	- state should be as local as possible (also with React Context, not with Redux or Jotai)
	- setState tells React to render  based on value (primitive) or reference change
	- becareful with State depending on other state -> use derived value instead https://www.youtube.com/watch?v=tz0fDABt67g&t=327s
	- useState [state, setState] -> state references the state, setState tells React to rerender with new object (keeps state immutable), state references new object at next rerender. setState(prev=>) prev references the actual state (meanwhile  state may only reference the old state object )
	- decide to useState (controlled input) or useRef (uncontrolled input) based on use-case https://www.youtube.com/watch?v=NZqMVUEiDIw
	- state as component in React rendering https://www.youtube.com/watch?v=vXJkeZf-4-4 --> key
- hooks
	- useLocalStorage
	- useDebounce
		- ![[Pasted image 20230628182241.png]]
- routing
	- ErrorBoundary problem with react router

***
## Notes
```
<React.Fragment key={i}></React.Fragment>

export default (props) => <Component {...props} />
```

```
import { useReducer } from "react";

const rows = [

  {

    id: "id-1",

    name: "Row 1",

  },

  {

    id: "id-2",

    name: "Row 2",

  },

  ...

];

// "history" is our stack

const initialState = { rows, history: [] };

function reducer(state, action) {

  switch (action.type) {

    case "remove":

      return {

        rows: removeRow(state, action),

        // Array.concat() as immutable alternative to Array.push()

        history: state.history.concat({

          action,

          row: state.rows[action.index]

        })

      };

    case "undo":

      return {

        rows: addRowAtOriginalIndex(state),

        // Array.slice() as immutable alternative to Array.pope()

        history: state.history.slice(0, -1)

      };

    default:

      throw new Error();

  }

}

function TableUsingStack() {

  const [state, dispatch] = useReducer(reducer, initialState);

  return (

    <>

      <button

        onClick={() => dispatch({ type: "undo" })}

        disabled={state.history.length === 0}

      >

        Undo Last Action

      </button>

      <table>

        <thead>

          <tr>

            <th>ID</th>

            <th>Name</th>

            <th></th>

          </tr>

        </thead>

        <tbody>

          {state.rows.map(({ id, name }, index) => (

            <tr key={id}>

              <td>{id}</td>

              <td>{name}</td>

              <td>

                <button onClick={() => dispatch({ type: "remove", id, index })}>

                  Delete

                </button>

              </td>

            </tr>

          ))}

        </tbody>

      </table>

    </>

  );

}
```