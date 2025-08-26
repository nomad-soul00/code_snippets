
# Code Snippets 

#### List of Handy code Snippets and functions..





![Logo](https://img.icons8.com/?size=50&id=108784&format=png&color=000000)
## 


#### Onchange functnion for fields in react.

```
   const onChange = (e) => {
        setcredentials(...credentials, {[e.target.name]: e.target.value})
    }

```
#### sending data from forntend to backend in react && sme for fetching data from backend
```
const [credentials, setcredentials] = useState({name: '', email: '', password: '',geolocation: '', phoneNumber: ''})

 const handleSubmit = async (e) => {
        e.preventDefault();
        const response = await fetch('http://localhost:5000/api/user', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body:JSON.stringify({
                name: credentials.name,
                email: credentials.email,
                password: credentials.password,
                address: credentials.geolocation,
                phoneNumber: credentials.phoneNumber
            })
        }); 
        const json = await response.json();
        console.log(json);

        if(!json.sucess){
            alert('Enter valid credentials')
        }
    }
```
#### Hashing password with bcrypt
```
import bcrypt from 'bcrypt';

const salt = await bcrypt.genSalt(10);
const securePassword = await bcrypt.hash(req.body.password, salt);

```
#### fetching a collection from a prebuilt database.
```
await mongoose.connect(mongoURI)
console.log("Connected to MongoDB successfully");
const fetched_data = await mongoose.connection.db.collection('food_items').find({}).toArray();
console.log(fetched_data);
```
#### search input using filter
```
<input className="form-control me-2" type="search" placeholder="Search" aria-label="Search" value={search} onChange={(e)=>{setSearch(e.target.value)}} />

 (foodItem.length !== 0) && foodItem.filter((item) => 
    (item.name.toLowerCase().includes(search.toLocaleLowerCase())))


```
   
 
    