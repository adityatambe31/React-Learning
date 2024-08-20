
Components --> These are independent and are reusable bits of code. They serve the same purpose as JS functions but work in Isolation and return HTML.

So syntax would be:
    function Component()
    {
        return (
            <div>Component
            </div>
        )
    }
    export Default Component
<------------------------------------------------->

There are Class based components and Functional based components.  


We can use component reuse it again & again.

Example creating a div for video and description, so once we create a basic structure we can then reuse it again & again.


<------------------------------------------------->
JSX --> This allows us to write HTML tags in React. It also makes it easier to write and add HTML tags in React

so Syntax would be:
    function App() {
        return <h1>Hi Adi</h1>;

    }
<------------------------------------------------->

Fragment --> this helps to wraps components. the preferred way of using Fragments is:
    <>
    <a></a>
    <p></p> 
    </>


so Syntax would be: 
    function App() {
        return 
        <Fragment>
        <h1>Hi Adi</h1>
        <p>This is a paragraph</p>
        </Fragment>;
    }

<------------------------------------------------->
One of the important Section..

Expression in JSX --> we can write expression inside curly braces. The expression can be a React variable or property or any other JS expression. The JSX will then execute & return the result.

Use case of JSX:
const myName = "Aditya Tambe";
  const multiply = (a, b) => a * b;
  const specialClass = "Simple-class";
  return (
    <>
      <h1>{myName}</h1>
      <h1>2 * 2 = {multiply(2, 2)}</h1>
      <p>Friends: {["Adi", "Vitaly"]}</p>
      <p className={specialClass}> this is a specialClass variable</p>
    </>
  );

<------------------------------------------------>


List --> We will render lists with some type of loops. The JS map() array method is generally preferred method

Use case of List:

 const userInfo = [
    { name: "adi", email: "tambeaditya22@gmail.com" },
    { name: "arya", email: "arya777@gmail.com" },
    { name: "ali", email: "alibaba@gmail.com" },
  ];

  return (
    <>
      {userInfo.map((user) => (
        <ul key={Math.random() * 10}>
          <li>{user.name}</li>
          <li>{user.email}</li>
        </ul>
      ))}
    </>;
<----------------------------------------------------------->

Props/Properties

--> Props are arguments passed into React Components 

--> Props are passed to components by HTML attributes

so the props are used like:

// function based components

const User = (props) => {
  console.log(props.name);
  return (
    <section>
      <img src={props.img} alt={props.name} />
      <h1>Name: {props.name}</h1>
      <h1>hobbies: {props.hobbies}</h1>
      <h1>Age: {props.age}</h1>
    </section>
  );
};
function App() {
  return (
    <>
      <User
        name="Aditya"
        img="https://riot-us.com/wp-content/uploads/2023/11/intro-1634607238.webp?w=780"
        age={21}
        hobbies={["coding", " ", "traveling"]}
      />
    </>
  );
}

export default App;
<----------------------------------------------------------->

Props Destructuring --> in this we provide the params and removed the props keyword. to destructure the props we need children. So in this case we have section as in parent and h1,img are its children


const User = (img, name, age, hobbies) => {
  return (
    <section>
      <img src={img} alt={name} />
      <h1>Name: {name}</h1>
      <h1>hobbies: {hobbies}</h1>
      <h1>Age: {age}</h1>
    </section>
  );
};


function App() {
  return (
    <>
      <User
        name="Aditya"
        img="https://riot-us.com/wp-content/uploads/2023/11/intro-1634607238.webp?w=780"
        age={21}
        hobbies={["coding", " ", "traveling"]}
      >
        <p>loremskfnsdibfisudhfsidbfisdbpidsb</p>
      </User>
    </>
  );
}

export default App;
<----------------------------------------------------------->

Conditional Rendering --> It is the same way we use the conditions in JS. For example we use operator like If or the conditional operator to create elements representing the current state and let React update the UI to match them


const ValidPassWord = () => <h1>Valid Password</h1>;
const InvalidPassWord = () => <h1>Invalid Password</h1>;

const Password = ({ isValid }) => {
  if (isValid) {
    return <ValidPassWord />;
  } else {
    return <InvalidPassWord />;
  }
};

function App() {
  return (
    <>
      <Password isValid={true} />
    </>
  );
}

export default App;
<----------------------------------------------------------->
We have logical operator so its example is:

const Cart = () => {
  const items = ["TWS", "SmartPhones", "RAM", "Cabinets"];

  return (
    <>
      <h1>Cart 🛒</h1>

      {/* conditonal operator */}
      
      {items.length > 0 && <h2>You have {items.length} in your cart</h2>}
      <ul>
        <h4>Products👇</h4>
        {items.map((item) => (
          <li key={Math.random()}>{item}</li>
        ))}
      </ul>
    </>
  );
};

function App() {
  return (
    <>
      <Cart />
    </>
  );
}

export default App;

<----------------------------------------------------------->
Ternary Operator

// Using the ternary operator
const ValidPassWord = () => <h1>Valid Password</h1>;
const InvalidPassWord = () => <h1>Invalid Password</h1>;

const Password = ({ isValid }) => {
  return isValid ? <ValidPassWord /> : <InvalidPassWord />;
};

function App() {
  return (
    <>
      <Password isValid={true} />
    </>
  );
}

export default App;

<----------------------------------------------------------->
Styles: Using CSS and provide the colors and changing the overall styling of elements

function App() {
  return (
    <section>
      <h1 style={{ color: "white", backgroundColor: "teal", padding: "2rem" }}>
        Inline Styling
      </h1>
    </section>
  );
}
export default App;

<----------------------------------------------------------->