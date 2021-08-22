# My Quick React Tutorial Notes

## 1. HOW TO INSTALL REACT.JS ?

### 1.1-Install Node JS
  The first step is to download the Node.js installer for Windows. Let’s use the latest Long Term Support (LTS) version for Windows and choose the 64-bit version, using the Windows Installer icon. https://nodejs.org
  After the installation, check the versions using the below commands.
  node -v
npm -v

### 1.2 Install Create-React-App Tool
Now we need to install a tool named create-react-app using NPM as global. This tool is used to create react applications easily from our system.
npm install -g create-react-app


### 1.3 Creating a New React Project
npx create-react-app my-app


## Introduction To React.JS
#### Necessary Libraries
- npm install --save react-router-dom
- npm install --save flatlist-react
- npm install --save react-select'
- npm install --save react-spinners
- npm install --save react-confirm-alert
- npm install --save react-icons
- npm install --save ag-grid-community

First, We have to use router library in App.js to navigate between pages.

```javascript
import { Switch, Route, Redirect } from 'react-router-dom';
import HomePage from './pages/HomePage';

class App extends Component {
    constructor(props){
        super(props);
        this.state={
            
        }
    }
    render(){
    return (
            <>
            <div>
                <div className="md:ml-64">
                    <Switch>
                        <Route exact path="/" component={HomePage} />
                    </Switch>
                    <Footer />
                </div>
              </div>
            
            </>
        );
      }
}

 export default App;
 
```
Let's create a page named 'HomePage' under the 'page' folder. And then run project. You'll see 'Hello World' in default page.
```javascript
import { Switch, Route, Redirect } from 'react-router-dom';

class HomePage extends Component {
    constructor(props){
        super(props);
        this.state={
            
        }
    }
    render(){
    return (
            <>
            <div>
                Hello World;
              </div>
            
            </>
        );
      }
}

 export default HomePage;
 
```
Before design HomePage, let's create a Login Page. And we have to add the name of Page to App.js

```javascript
import { Switch, Route, Redirect } from 'react-router-dom';

class LogIn extends Component {
    constructor(props){
        super(props);
        this.state={
            
        }
    }
    render(){
    return (
            <>
            <div>
                <div className="flex flex-wrap mt-10">
            <div className="w-full lg:w-6/12 pr-4 mb-10 font-light">
                <Input
                    type="text"
                    color="purple"
                    placeholder="Username"
                    onChange={(e) => {this.handleChange("userName",e)}}
                />
            </div>
        </div>
        <div className="flex flex-wrap mt-10">
            <div className="w-full lg:w-6/12 pr-4 mb-10 font-light">
                <Input
                    type="text"
                    color="purple"
                    placeholder="Password"
                    onChange={(e) => {this.handleChange("password",e)}}
                />
            </div>
        </div>
        <Button onClick={()=>this.adminLogin()}>Giriş</Button>
              </div>
            
            </>
        );
      }
}

 export default LogIn;
 
```
See Router.

```javascript
<Switch>
   <Route exact path="/" component={HomePage} />
</Switch>
```

Now, let's design our HomePage. 
We'll use  Ag-Grid, select and basic other components with some local .Json files.



```javascript

const users = [
  {
    _id: 'ab12ex',
    username: 'Alex',
    email: 'alex@alex.com',
    password: '123123',
    createdAt: '08/01/2020 9:00 AM',
    isLoggedIn: false,
    name :Alex,
    surname:Edward
  },
  {
    _id: 'fg12cy',
    username: 'Asab',
    email: 'asab@asab.com',
    password: '123456',
    createdAt: '08/01/2020 9:30 AM',
    isLoggedIn: true,
  },
  {
    _id: 'zwf8md',
    username: 'Brook',
    email: 'brook@brook.com',
    password: '123111',
    createdAt: '08/01/2020 9:45 AM',
    isLoggedIn: true,
  },
  {
    _id: 'eefamr',
    username: 'Martha',
    email: 'martha@martha.com',
    password: '123222',
    createdAt: '08/01/2020 9:50 AM',
    isLoggedIn: false,
  },
  {
    _id: 'ghderc',
    username: 'Thomas',
    email: 'thomas@thomas.com',
    password: '123333',
    createdAt: '08/01/2020 10:00 AM',
    isLoggedIn: false,
  },
]

const products = [
  {
    _id: 'eedfcf',
    name: 'mobile phone',
    description: 'Huawei Honor',
    price: 200,
    ratings: [
      { userId: 'fg12cy', rate: 5 },
      { userId: 'zwf8md', rate: 4.5 },
    ],
    likes: [],
  },
  {
    _id: 'aegfal',
    name: 'Laptop',
    description: 'MacPro: System Darwin',
    price: 2500,
    ratings: [],
    likes: ['fg12cy'],
  },
  {
    _id: 'hedfcg',
    name: 'TV',
    description: 'Smart TV:Procaster',
    price: 400,
    ratings: [{ userId: 'fg12cy', rate: 5 }],
    likes: ['fg12cy'],
  },
]
```
