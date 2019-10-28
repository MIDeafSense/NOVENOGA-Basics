### **Description**

Hi Pilot ! 

Cyberspace.dev is first online game for developers! In the game, you are the control center of spaceships in the universe, the game has a fairly simple game model and does not require much time to start. This is an excellent platform for both manned control and for the development of automation scripts and even artificial intelligence!

### **Limitations**

The API limits the number of executed <b>commands to 5 per sec</b>, you will be disconnected if you exceed these limits.

### **Quick start**

Install module as npm package

```typescript
npm install @cyberspace-dev/sdk
```

1. Connect to account service and signin

```typescript
const account = await SDK.Account.connect();
await account.signin('email@mail.com', 'password');
```

2. Look at what objects you own and select any ship

```typescript
const objects = await account.objects();
const target = objects.find((instance: any) => instance.type === 'Ship');
```

3. Take control over your ship

```typescript
const quadrant = await SDK.Sector.connect(target.realm, account.token);
const ship = await quadrant.get(target.uuid); 
```

4. Escape from the planet and move to any point in the system

```typescript
await ship.escape();
await ship.move(800, 800);
```

Congratulations ! Please read our wiki.
