
Day 6-2
Composition vs Inheritance

React has a powerful composition model, and 
recommended using composition instead of inheritance to reuse code between components.

Containment: This lets other components pass arbitrary children to them by nesting the JSX:    {props.children}
function FancyBorder(props) {
  return (
    <div className={'FancyBorder FancyBorder-' + props.color}>
      {props.children}
    </div>
  );
}

function WelcomeDialog() {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        Welcome
      </h1>
      <p className="Dialog-message">
        Thank you for visiting our spacecraft!
      </p>
    </FancyBorder>
  );
}


React elements are just like objects, we can pass that as a props like any other data



Specialization : special case of other components
ex: WelcomeDialog  is special case of Dialog

In React, this is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props:



If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module. The components may import it and use that function, object, or a class, without extending it.
