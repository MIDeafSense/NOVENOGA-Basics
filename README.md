### **Description**

Hi Pilot ! 

Cyberspace.dev is the first online game for developers! In the game, you are the control center of spaceships in the universe. The game has a fairly simple game model and does not require much time to start. This is an excellent platform for both manned control and development of automated scripts and even artificial intelligence!

Our website: https://cyberspace.dev

### **Quotas**

Max requests: <b>5</b> p/s<br/>
Max connections: <b>100</b></b>

### **Quick start**

Install module as npm package

```typescript
npm install @cyberspace-dev/sdk
```

Connect to account service and signin

```typescript
const account = await Account.connect();
await account.signin('email@mail.com', 'password');
```

Look at what objects you own and select any ship

```typescript
const objects = await account.objects();
const target = objects.find((instance: any) => instance.type === 'Ship');
```

Take control over your ship

```typescript
const quadrant = await Sector.connect(target.realm, account.token);
const ship = await quadrant.get(target.uuid); 
```

Escape from a planet and move to any point in the system

```typescript
await ship.escape();
await ship.move(800, 800);
```

Congratulations! Please read our wiki: https://github.com/cyberspace-dev/cyberspace-sdk/wiki
