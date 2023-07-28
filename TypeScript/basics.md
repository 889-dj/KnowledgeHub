
Typescript 
Note - whenever declaring other types of interface etc we start our varName using capital letter


1) Variables in TS
- Javascript var declaration=> let varname = value 
- Typescript var declaration=> let varname: type = value 
- Primitive types => number , Boolean , string 
- Any(type) keyword  => use when don't knw the type of var or I don't wanna do type checking 
- Typescript automatically infer the type of a variable on initialisation by default it's any (not gud in practice)

2) Functions in TS
- function funcName( var : type): type {......}
- Const arrfunc = (varname : type) : type => {.......} 
- Type checking is shown/visible one item at a time 

3) Objects in TS
- Passing & returning objects in functions 
  - function funcName({...}) : {...obj} {.............}

- odd behaviour of objects in typescript
Eg : createUser( {name: string , isPaid: boolean} )
Not accepted :-
      createUser ( {name:"dj" , isPaid:false , email:"h@h.com"} )  [passing extra prop to the object directly to function will give error]
Accepted :-
     Let newUser = {name:"dj" , isPaid:false ,    email:"h@h.com"}
createUser( newUser )  [ declaring objects outside func and then passing it will not give error ]

4) Type Aliases in TS
- Using the 'type' keyword we can make aliases 
Type mytype = object / type 

- Never is used when we need to handle errors (refer docs for further explanation)[ never is something which is never supposed to execute or end the things ]

- readonly _id [readonly make the var inaccessible to others cannot be accessed by outsiders]
- Credcarddetails ?: string  [ using the ? After the var make it optional ]
- & [ampersand is used to mix and match 2 or more than 2 types of data ]
Eg : type cardDate = {cardDate: string} , type win = {win: Boolean}
(Creating new type) -> type cardDetails =  cardDate & win and {CVV: number}

5) Arrays in TS
- Const arrName : type[] = []
- Const arrName : Array<type> = []
- We can also build a array of custom type using alias 
- creating array of arrays in TS 
   Const arrName : type[][] = []

6)  Union type in TS ( | )
*Instead of any try to use union 
- Union is a combination >=2 types that u can include in variable, array , etc.
- let varName : number | string | Boolean | customType(using type )
- when using union types it creates a new type that can be either type1 or type2 n so on so we need to check the type in our functions or loops or whatever
- Arrays with union types 
   Const varName : (type1 | type2)[] = []
Another usecase : eg-
Let Seatallotment : "aisle" | "middle" | "window"
Seatallotment = "aisle"    ✅
Seatallotment = "crew"    ❎
Only the types/value that are provided are allowed 

7) Tuples in TS
- Special kind of array with some restriction on it 
- Const tuple : [type1 , type2 ,type3]
   tuple = [valtype1 , valtype2 , valtype3] ✅
- The order of types in declaration and values must be same ( [valtype2 , valtype1 , valtype3] ❎
- tuple make sure not just what's inside array but the order also matters
- eg: rgb : [number , number , number ] = [255,255,255]
- We can make custom tuple types 
Eg : type User = [number ,string ]
Const newUser = [112,"dj"]
- We can push more elements at the back of it that's a weird behaviour read about it online 

8) Enums is TS
- enum seatchoice = {
AISLE=10 , MIDDLE ,WINDOW , FOURTH 
}
- by default the value of first member of enum is 0 and then increasing order but we can provide Any type (string number etc) to any of the members 
- It is used to limit our choices we can access it like :
Const seat = seatchoice.AISLE ( AFTER . WE WILL BE SHOWN ONLY THE OPTION IN OUR ENUM)
- using Enums create a lot of js code to avoid that we can use comst -> const enum varName = {....}

9) Interfaces in TS (interface keyword)
- Much similar to types or a loose form of class as it allows u to have methods
- what makes interfaces interesting is the def of functions 
- interface user {
   email : string 
   Userid : number 
   Starttrial : () => string(type) // method1  of defining    func in interfaces 
    GetCoupon() : number // method2 of defining func in interfaces
}

10) Advantages of interface 
- We can extend our interface that is we can add more properties to it without touching the actual interface we need to just add a property using the above syntax ( and this is called reopening of interface.
interface user { GitHubtoken : string } //this is added to the above original Interface
- interface also give us the advantage of inheritance
Interface admin extends user {} // using extends keyword (see the docs and Google)
- type aliases can't be modified once created and to extend type we use &(ampersand)

See the difference between type aliases and interface from the documentation


11) How to setup Typescript for real world project 
- tsc --init  >  it creates a simple typescript config file 
- U can see all the options either from the documentation or it is commented in the tsconfig.json file 

12) classes in TS
- To use the variable inside the constructor we need to declare them outside the constructor 
- Declare every variable before using 
Class user {
    email : string 
    name: string
    Constructor(email: string, name: string){
     This.email = email ;
     This.name = name ; 
     }
}
Const newuser = new  user('h@h
Com' , 'dj')

- Typescript way of declaring class 
Class user{
      SomeVar: type = val
    Constructor(public email:string , public name: string, private userid: string) {.........}
}

12) why interface are imp 
Interface takephoto{.......}
Class cameraapp implements takephoto {........}

13)  Abstract classes in TS
- Abstract classes are like interfaces we can make a class abstract using 'abstract' keyword
- Abstract classes cannot create obj of their own 
- They help to define the class who are inheriting them 

14) Generics 
- function  genericFunc<Type>(val: Type): Type{........}
- function  genericFunc<T>(val: T[]): T{........}
- const funcName =  <T>(val: T): T => {........}
- We can use our own made types/interface in the generics 
- in the above syntax we can put coma this is to distinguish between generic and others  ->  <T,>

15) generic classes 
16) in operator and type narrowing in TS
Read about them from the documentation/online 
* Is as in operators in TS 

17)  Instanceof and Type predicates 
- Typeof check for the default types 
- Anything that can be constructed with new keyword that's where Instanceof comes into the picture 
- Instanceof checks whether a object is a instance of a class 

18) Discriminated union and the exhaustiveness checking with never (part of narrowing )
- The process of refining types to more specific types than declared is called narrowing 
- eg: in case of union types we need to check for the specific type to perform a operation on particular type [ var something : (string | number ) then to perform a operation specifically for number of for string we need to check for whether it's a number or a string & this is called type guard 

Type of typeguards : 
String , Number , bigint , Boolean , symbol , undefined , object , function 




Scoping in typescript?


```
// variable in ts 
let something :number = 20;

// function in ts 
function tellnum(n:number):number {
  console.log(n)
  return n;
}
// tellnum(something)
const msg = (msg :string):string =>{
  console.log( `your message is ${msg}`)
  return `your message is ${msg}`
}
// msg('something')

// object in ts 
let obj:{name:string,iscustomer:boolean}= {
name: "dev",
iscustomer: false
}

// type alsiasing in ts using 'type' keyword
type User = {
  readonly _id:number;
  name:string;
  phno:number;
  iscustomer:boolean
}
let user: User = {_id:444,name:'dev',phno:57757657657,iscustomer:true}

// array in ts
const arr:string[] = ['hii']
const arr2:Array<string> = ['hii']
const arr3:User[] = []

//union types in ts (|)
let User1 :'admin'|'user'|'something'
let S : boolean|User|number

// User1 = 'crew'

// tuple in ts
let tuple :[string,boolean,number,number];
tuple = ['',true,4,5] 

// enums in ts
const enum xy {
  one = 'yu',
  tw0=8,
  three = 90,
  four,
}
// console.log(xy.one)

// interfaces in ts
interface me {
  name:string;
  age:number;
  profession:string;
}
const dj:me = {
  name:"dev",age:21,profession:'react developer'
}

// intersecion type in ts using '&'
interface Colorful {
  color: string;
}
interface Circle {
  radius: number;
}
 
type ColorfulCircle = Colorful & Circle;



// console.log(dj)


// Classes , private & public access identifiers
// class Xuser{
// public email:string;
// private name:string;
// readonly city:string
//   constructor(email:string,name:string,city:string){
//     this.email = email;
//     this.name = name;
//     this.city = city;
//   }
// }

class Xuser{
  // private _coursecount = 1
  protected _coursecount = 1
readonly city:string = "gwalior"
  constructor(public email:string,public name:string,private userID:string){
    
  }
  //private method
  private deltoken(){
    console.log('token')
  }
  //getter
  get getappleemail():string{
    return `apple ${this.email}`
  }
  get courseCount():number{
    return this._coursecount
  }
  //setter
  set courseCount(courseNum){
    if(courseNum<=1)throw new Error("course count should be more than one")
    this._coursecount = courseNum 
  }
}

//inheritance example using 'extends' keyword
class Subuser extends Xuser{
  isFamily:boolean=true
  changecoursecount(){
    this._coursecount = 4
  }
}
const dp = new Xuser('h@h.com','dj','gwalior')
dp.city
```