### **Description**

Hi Pilot ! 

Cyberspace.dev - online game for developers! The game has a fairly simple game model and does not require much time to start. This is an excellent platform for both manned control and for the development of automation scripts and even artificial intelligence!

Our website: https://cyberspace.dev

### **Quotas**

Max requests: <b>5</b> p/s <br/>
Max connections: <b>25</b> p/ip

### **Quick start**

Install module as npm package

```typescript
npm install @cyberspace-dev/sdk
```

Import type from package

```typescript
import {Account} from "@cyberspace-dev/sdk";
```

Connect to account service and signin

```typescript
const account = await Account.connect();
await account.signin('your@email.com', 'password');
```

Look at what objects you own and select any ship

```typescript
const objects = await account.objects();
const instance = objects.find((object: any) => object.type === 'Ship');
```

Take control over your ship

```typescript
const {uuid, quadrant} = instance;
const ship = await account.getShip(uuid, quadrant);
```

Escape from the planet and move to any point in the system

```typescript
await ship.escape();
await ship.move(800, 800);
```

You can dispose the ship if you no longer need it because it consumes 1 connection

```typescript
ship.dispose();
```

Congratulations!<br /> Please read our wiki: https://github.com/cyberspace-dev/cyberspace-sdk/wiki<br />
You also can download the starter project from https://cyberspace.dev/assets/starters/starter.zip
