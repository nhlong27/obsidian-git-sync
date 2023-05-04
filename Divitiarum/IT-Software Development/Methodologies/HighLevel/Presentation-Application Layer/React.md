[#react]
[Roadmap](https://roadmap.sh/react)

**Server State Management / API Layer**
	React Query (wrapper of promise-based request (axios/fetch))
**Client State Management**
**Presentation**
	Routing

helper methods/functions
naming 'polymorphic' props: styles, "flags"(boolean), role, function
When to use type predicates


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