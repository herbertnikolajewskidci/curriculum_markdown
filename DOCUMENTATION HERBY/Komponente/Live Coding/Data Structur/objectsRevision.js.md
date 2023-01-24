```JavaScript
// digitalcareerinstitute Emails
const dci = {
  users: [
    {
      _id: 12334,
      name: "Ghassan",
      email: "ghassan@digitalcareerinstitute.de",
      password: 123456,
      isAdmin: false,
      date: new Date(),
    },
  ],
};

// CRUD  ==> C = create, R = read, U= update ,
// D = delete
// insert new user
const genUserId = () => {
  const genId = Math.floor(Math.random() * 10000);
  return genId;
};

// const genUserId = () => Math.floor(Math.random() * 10000) // same
// 1 and 10000
function createUser(user) {
  // user shall be object
  //code to add the user to DB
  // create a valid user
  if (typeof user == "object") {
    const newUser = {
      _id: genUserId(),
      date: new Date(),
      email: user.name.toLowerCase() + "@digitalcareerinstitute.de",
      name: user.name,
      password: user.password,
      isAdmin: user.isAdmin,
    };
    //push the new user to our DB
    dci.users.push(newUser);
  } else {
    console.log("the user is not valid :(");
  }
}

createUser({
  name: "Maja",
  password: 87965,
  isAdmin: true,
});

createUser({
  name: "Bayo",
  password: 64778,
  isAdmin: true,
});

createUser("haha");
createUser("haha");
console.log(dci.users);

// console.log("genUserId ==> ", genUserId());
// console.log("genUserId ==> ", genUserId());
// console.log("genUserId ==> ", genUserId());
// console.log("genUserId ==> ", genUserId());

// create a function to get all the admins users
function getAdmins() {
  //code
}

console.log(getAdmins());
```