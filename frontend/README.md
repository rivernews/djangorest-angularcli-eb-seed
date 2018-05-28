# Angular + Material Design Component

[Angular Hero Tutorial](https://angular.io/tutorial)
[Angular Material Getting Started](https://material.angular.io/guide/getting-started)
[Our Angular Notebook](https://medium.com/p/763e5d938b39/edit)

## Adding Angular Routing Function

[add routing module](https://angular.io/tutorial/toh-pt5#add-the-approutingmodule)

1. `ng generate module app-routing --module=app`
  - in `app-routing.module.ts ` you can delete the `commonModule` and `declarations` stuff.

1. in `app-routing.module.ts`

```
...
import { RouterModule, Routes } from '@angular/router';

// import components
import { HeroesComponent } from './heroes/heroes.component';

const routes: Routes = [
  { path: '', redirectTo: '/dashboard', pathMatch: 'full' },
  { path: 'dashboard', component: DashboardComponent },
  { path: 'heroes', component: HeroesComponent },
  { path: 'detail/:id', component: HeroDetailComponent }, // routing w/ a parameter
];

@NgModule({
  imports: [ RouterModule.forRoot(routes) ], // configure the router at the application's root level
  exports: [ RouterModule ],
})
export class AppRoutingModule { }
```

1. add `<router-outlet></router-outlet>` in `app.component.html`

1. whenever you want to route through a link, you can now do 

```
<a routerLink="/heroes">Heroes</a>
```

## Adding new view (page) and route to it

[adding a view](https://angular.io/tutorial/toh-pt5#add-the-dashboard-route)

1. `ng generate component dashboard`

1. add component's html, configure its ts.

1. in routing ts import the component, then register a routing path for that component

1. add link to route to that component, if needed.