---
title: Custom ID
permalink: /next/angular-custom-id
canonicalUrl: /angular-custom-id
---

# Custom ID

You can easily pass `id` and other attributes to the `hot-table` wrapper element.
It will be applied to the root Handsontable element, allowing further customization of the table.

::: example #example1 :angular
```js
// app.component.ts
import { Component } from '@angular/core';
import * as Handsontable from 'handsontable';

@Component({
  selector: '#example1',
  template: `
  <div class="hot">
    <hot-table
      [settings]="hotSettings"
      [hotId]="id">
    </hot-table>
  </div>
  `,
})
class AppComponent {
  hotSettings: Handsontable.GridSettings = {
    startRows: 5,
    startCols: 5,
    colHeaders: true,
    stretchH: 'all'
  };
  id = 'my-custom-id';
}

// app.module.ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HotTableModule } from '@handsontable/angular';

@NgModule({
  imports:      [ BrowserModule, HotTableModule ],
  declarations: [ AppComponent ],
  bootstrap:    [ AppComponent ]
})
class AppModule { }

// bootstrap
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

platformBrowserDynamic().bootstrapModule(AppModule).catch(err => { console.error(err) });
```
:::