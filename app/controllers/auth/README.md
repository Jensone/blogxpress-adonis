# BlogXpress

## Création du projet
```bash
pnpm create adonisjs@latest blogxpress
```

```bash
code blogxpress
```

```bash
pnpm run dev
```


## Création des routes

```bash
# start/routes.ts
...

import LoginController from '#controllers/auth/login_controller'
import LogoutController from '#controllers/auth/logout_controller'
import RegisterController from '#controllers/auth/register_controller'

router.on('/').render('pages/home').as('home')
router.group(() => {
  // Registration
  router.get('/register', [RegisterController,'show']).as('register.show')
  router.post('/register', [RegisterController,'store']).as('register.store')

  // Login
  router.get('/login', [LoginController,'show']).as('login.show')
  router.post('/login', [LoginController,'store']).as('login.store')

  // Logout
  router.post('/logout', [LogoutController,'getOut']).as('logout')
}).as('auth')
```


## Création des controllers associés aux routes

```bash
node ace make:controller auth/register show store -s
```

```bash
node ace make:controller auth/login show store -s
```

```bash
node ace make:controller auth/logout getOut -s
```


## Création des vues

```bash
node ace make:view pages/auth/register
```

```bash
node ace make:view pages/auth/login
```

```bash
node ace make:view pages/auth/logout
```

```bash
node ace make:view components/layout/main
```
