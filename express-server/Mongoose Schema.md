```javascript 
  const mongoose = require('mongoose');
  const userSchema = new mongoose.Schema({
    name: {
       type: String,
       required: true,
    },
    userName:{
        type:String,
        required:[true, 'Username is required!'],
        unique:true,
        trim:true,
    },
    email:{
        type:String,
        required:[true, 'Email is required!'],
        unique:true,
        validate: {
           validator: function (value) {
              return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value);
           },
           message: 'Invalid email format',
        }
    },
    phone: {
      type: String,
    },
    password: {
      type: String,
      required: true,
      minlength: 6, // Example: Minimum password length is 6 characters
    },
    image:{
      type: String,
    },
    address: {
      type: String,
    },
    isAdmin : {
       type: Boolean,
       default: false,
    },
    isBanned : {
      type: Boolean,
      default: false,
    }
},

{
  timestamps: true;
})


const User = mongoose.model('User', userSchema)

module.exports = User;
```

#Mongoose_Schema #Users_Schema
