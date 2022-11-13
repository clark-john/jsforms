---
title: Getting Values from a Form
---

# Getting Values from a Form

```html
<!-- app.component.html -->
<form>
	<input type="text">
	<input type="password">
	<input type="submit" value="Submit">
</form>
```

## Configuring

Register `FormsModule` to your root module

```ts{1,13}
import { FormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    AppComponent,
    IndexPage,
    NotfoundPage
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule,
    FormsModule, 
    BrowserAnimationsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

### using NgModel

```ts
import { Component, OnInit, HostListener } from '@angular/core';

@Component({
	templateUrl: "./app.component.html",
	selector: 'app-root'
})
export class AppComponent implements OnInit {
	// create variables 
	name: string = "";
	password: string = "";

	// add listener to this component
	@HostListener("submit")
	showValues(e: Event /* you can also omit this param */){
		alert(JSON.stringify({
			name: this.name,
			password: this.password
		}));
	}
	// on component load lifecycle
	ngOnInit(): void {}
}

```
```html
<form>
	<!-- bin these two values to ngModel and always add the "name" attribute -->
	<input type="text" [(ngModel)]="name" name="name">
	<input type="password" [(ngModel)]="password" name="password">
	<input type="submit" value="Submit">
</form>
```

### using FormControl

```ts
// soon
```