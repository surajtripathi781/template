---


---

<h1 id="angular">Angular</h1>
<p><strong>create App</strong><br>
<em><code>npx create-react-app &lt;my-app&gt;</code></em><br>
<strong>Start App</strong><br>
<em><code>npm start</code></em><br>
*<strong>npx</strong> is package runner installed when <strong>npm</strong> install<br>
<code>npm install create-react-app -g</code></p>
<h2 id="component">Component</h2>
<p>2 Types:-</p>
<p><em>Stateless</em></p>
<pre><code>import  React  from  'react'
//1.export const Greet=()=&gt; &lt;h1&gt;Welcome Sir!&lt;/h1&gt;
const  Greet=()=&gt;  &lt;h1&gt;Welcome  Sir!&lt;/h1&gt;
export  default  Greet;
</code></pre>
<p><em>Statefull</em></p>
<pre><code>import  React,  {  Component  }  from  "react";
class  Welcome  extends  Component{
render(){
    return  &lt;h1&gt;Welcome  RJS&lt;/h1&gt;
    }
}
export  default  Welcome;
</code></pre>
<p><em>How to use component</em></p>
<pre><code>import  Welcome  from  './controllers/Welcome';
class  App  extends  Component  {
render(){
   return(
	    &lt;div&gt;
		    &lt;Welcome/&gt;
	    &lt;/div&gt;
	    );
   }
 }	
render(&lt;App /&gt;, document.getElementById('root'));
</code></pre>
<p>*Note:-Statefull component have enrich in feature with state and handle complex UI logic.</p>
<h3 id="jsx"><s>JSX</s></h3>
<p>JavaScript XML Write XML-like code for elements and component.<br>
JSX is not necessary to write React App<br>
JSX transpile to pure JS code.</p>
<pre><code>return  React.createElement('div',null,'&lt;h1&gt;Hello Mr.&lt;/h1&gt;')
</code></pre>
<p><img src="https://cdn1.imggmi.com/uploads/2019/12/17/1a7337392f1b865dfdc4739face3f4d8-full.png" alt=""></p>
<pre><code>return  React.createElement('div',
{id:'hello',className:'DummyClass'},//id,class,style etc add to each node
React.createElement('h1',null,'Hello Mr.'))
</code></pre>
<p><img src="https://cdn1.imggmi.com/uploads/2019/12/17/e9d558a20427f011c2e0437acd05cd45-full.png" alt="enter image description here"></p>
<h2 id="props">Props</h2>
<p>Props is short of properties.<br>
It is optional input that your component can accept and allow the component content to be dynamic</p>
<pre><code>*App.js*

&lt;Greet name="React" homeName="Bad Practice"&gt;
&lt;p&gt;Hello Paragraph&lt;/p&gt; (1.)--is children props
&lt;/Greet&gt;
&lt;Welcome name="T" homeName="E"/&gt;

*Greet.js*

	const  Greet=(props)=&gt;  {
	console.log(props)
	return  (
	&lt;h1&gt;Welcome  Sir!  {props.name}&lt;/h1&gt;
	{props.children}
)
}
</code></pre>
<p><em>Welcome.js</em></p>
<pre><code>class  Welcome  extends  Component{
render(){
    return  &lt;h1&gt;Welcome  RJS  {this.props.name}  {this.props.homeName}&lt;/h1&gt;
    }
}
</code></pre>
<p>export  default  Welcome;</p>
<p>Note*:- JSX should content only one wrapper<br>
props are immutable i.e can’t assign new value to props e.g.</p>
<pre><code>props.name='Change Name'   //give error
</code></pre>
<h2 id="state">State</h2>
<p><em>vs/Props</em><br>
- props passed to the component whereas state is managed within  the<br>
component.<br>
- Function Parameter vs var declared in component body<br>
- props as immutable/readonly vs state can be changed<br>
- props-this.props vs useState hook-this.state</p>
<pre><code>class  Message  extends  Component{    
constructor(){    
    super()    
    this.state={    
	    message:'Welcome Visitor'    
	    }    
    }
increment(){
    this.setState({
    count:this.state.count+1
  })
  
  //this.state.count=this.state.count+1;
  
  /*this.setState(prevState=&gt;({
	count:prevState.count+1
	}))*/
	
  console.log(this.state.count)
}
      
render(){    
   return(
	    &lt;div&gt;
			&lt;h1&gt;{this.state.message}&lt;/h1&gt;
			&lt;button type="button" onClick={ ()=&gt;this.increment() }&gt;Increment&lt;/button&gt;
		&lt;/div&gt;
	)
}    
}
</code></pre>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Never modify state directly e.g <code>this.state.count=this.state.count+1</code></li>
</ul>
<h3 id="destructuring">Destructuring</h3>
<p><em>Functional Component</em></p>
<pre><code>const Greet=({name,heroName})=&gt;{
return(
    &lt;div&gt;
	&lt;h1&gt;Hello {name} {heroName}&lt;/h1&gt;	
	&lt;/div&gt;
	)
}


const Greet=(props)=&gt;{
const {name,heroName}=props
return(
    &lt;div&gt;
	&lt;h1&gt;Hello {name} {heroName}&lt;/h1&gt;	
	&lt;/div&gt;
	)
}
</code></pre>
<p><em>Class Component</em></p>
<pre><code>class  Welcome  extends  Component{
render(){
    const {name,heroName}=this.props
    //const {state1,state2}=this.state
    return  &lt;h1&gt;Welcome  RJS  {this.props.name}  {this.props.homeName}&lt;/h1&gt;
    }
}
</code></pre>
<h3 id="event-handling">Event Handling</h3>
<p><em>Functional component</em></p>
<pre><code>function FuncClick(){
	console.log('clicked')
}
return(
&lt;div&gt;
&lt;button onClick={FuncClick()}&gt;&lt;/button&gt;
&lt;button onClick={FuncClick()}&gt;&lt;/button&gt;
&lt;/div&gt;
)
</code></pre>

