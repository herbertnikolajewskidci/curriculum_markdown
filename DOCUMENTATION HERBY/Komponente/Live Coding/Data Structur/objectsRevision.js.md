```JavaScript
// digitalcareerinstitute Emails DB
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

// CRUD  ==> C = create, R = read, U= update , D = delete
// neuen Benutzer einfügen
const genUserId = () => {
    const genId = Math.floor(Math.random() * 10000);
    return genId;
};

// const genUserId = () => Math.floor(Math.random() * 10000) // Zahl zwischen 1 und 10000
function createUser(userObjAsParam) {
    // Benutzer soll Objekt sein
    // schreibe einen Code zum Hinzufügen eines Benutzers in eine DB
    // einen gültigen Benutzer anlegen
    if (typeof userObjAsParam == "object") {
        const newUser = {
            _id: genUserId(),
            date: new Date(),
            email:
                userObjAsParam.name.toLowerCase() +
                "@digitalcareerinstitute.de",
            name: userObjAsParam.name,
            password: userObjAsParam.password,
            isAdmin: userObjAsParam.isAdmin,
        };
        // den neuen Benutzer in unsere DB aufnehmen
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

// eine Funktion erstellen, die alle Admins-Benutzer ermittelt
function getAdmins() {
    const adminUsers = [];
    // dci.users.forEach(
    //     ({ name, isAdmin }) => isAdmin && adminUsers.push({ name, isAdmin })
    // );
    for (const { name, isAdmin } of dci.users) {
        if (isAdmin) {
            adminUsers.push({ name, isAdmin });
        }
    }
    return adminUsers;
}

console.log(getAdmins());

```