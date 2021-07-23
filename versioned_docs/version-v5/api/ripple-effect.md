---
sidebar_label: "ion-ripple-effect"
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# ion-ripple-effect

The ripple effect component adds the [Material Design ink ripple interaction effect](https://material.io/develop/web/components/ripples/). This component can only be used inside of an `<ion-app>` and can be added to any component.

It's important to note that the parent should have [relative positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position) because the ripple effect is absolutely positioned and will cover the closest parent with relative positioning. The parent element should also be given the `ion-activatable` class, which tells the ripple effect that the element is clickable.

The default type, `"bounded"`, will expand the ripple effect from the click position outwards. To add a ripple effect that always starts in the center of the element and expands in a circle, add an `"unbounded"` type. It's recommended to add `overflow: hidden` to the parent element to avoid the ripple overflowing its container, especially with an unbounded ripple.

## Usage

<Tabs defaultValue="angular" values={[{ value: 'angular', label: 'ANGULAR' }, { value: 'javascript', label: 'JAVASCRIPT' }, { value: 'react', label: 'REACT' }, { value: 'stencil', label: 'STENCIL' }, { value: 'vue', label: 'VUE' }]}>


<TabItem value="angular">

```html
<ion-app>
  <ion-content>
    <div class="ion-activatable ripple-parent">
      A plain div with a bounded ripple effect
      <ion-ripple-effect></ion-ripple-effect>
    </div>

    <button class="ion-activatable ripple-parent">
      A button with a bounded ripple effect
      <ion-ripple-effect></ion-ripple-effect>
    </button>

    <div class="ion-activatable ripple-parent">
      A plain div with an unbounded ripple effect
      <ion-ripple-effect type="unbounded"></ion-ripple-effect>
    </div>

    <button class="ion-activatable ripple-parent">
      A button with an unbounded ripple effect
      <ion-ripple-effect type="unbounded"></ion-ripple-effect>
    </button>
  </ion-content>
</ion-app>
```

```css
.ripple-parent {
  position: relative;
  overflow: hidden;
}
```

</TabItem>


<TabItem value="javascript">

```html
<ion-app>
  <ion-content>
    <div class="ion-activatable ripple-parent">
      A plain div with a bounded ripple effect
      <ion-ripple-effect></ion-ripple-effect>
    </div>

    <button class="ion-activatable ripple-parent">
      A button with a bounded ripple effect
      <ion-ripple-effect></ion-ripple-effect>
    </button>

    <div class="ion-activatable ripple-parent">
      A plain div with an unbounded ripple effect
      <ion-ripple-effect type="unbounded"></ion-ripple-effect>
    </div>

    <button class="ion-activatable ripple-parent">
      A button with an unbounded ripple effect
      <ion-ripple-effect type="unbounded"></ion-ripple-effect>
    </button>
  </ion-content>
</ion-app>
```

```css
.ripple-parent {
  position: relative;
  overflow: hidden;
}
```

</TabItem>


<TabItem value="react">

```tsx
import React from 'react';
import { IonApp, IonContent, IonRippleEffect } from '@ionic/react';
import './RippleEffectExample.css';

export const RippleExample: React.FC = () => (
  <IonApp>
   <IonContent>
      <div className="ion-activatable ripple-parent">
        A plain div with a bounded ripple effect
        <IonRippleEffect></IonRippleEffect>
      </div>

      <button className="ion-activatable ripple-parent">
        A button with a bounded ripple effect
        <IonRippleEffect></IonRippleEffect>
      </button>

      <div className="ion-activatable ripple-parent">
        A plain div with an unbounded ripple effect
        <IonRippleEffect type="unbounded"></IonRippleEffect>
      </div>

      <button className="ion-activatable ripple-parent">
        A button with an unbounded ripple effect
        <IonRippleEffect type="unbounded"></IonRippleEffect>
      </button>
    </IonContent>
  </IonApp>
);
```

```css
.ripple-parent {
  position: relative;
  overflow: hidden;
}
```

</TabItem>


<TabItem value="stencil">

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'ripple-effect-example',
  styleUrl: 'ripple-effect-example.css'
})
export class RippleEffectExample {
  render() {
    return [
      <ion-app>
        <ion-content>
          <div class="ion-activatable ripple-parent">
            A plain div with a bounded ripple effect
            <ion-ripple-effect></ion-ripple-effect>
          </div>

          <button class="ion-activatable ripple-parent">
            A button with a bounded ripple effect
            <ion-ripple-effect></ion-ripple-effect>
          </button>

          <div class="ion-activatable ripple-parent">
            A plain div with an unbounded ripple effect
            <ion-ripple-effect type="unbounded"></ion-ripple-effect>
          </div>

          <button class="ion-activatable ripple-parent">
            A button with an unbounded ripple effect
            <ion-ripple-effect type="unbounded"></ion-ripple-effect>
          </button>
        </ion-content>
      </ion-app>
    ];
  }
}
```

```css
.ripple-parent {
  position: relative;
  overflow: hidden;
}
```

</TabItem>


<TabItem value="vue">

```html
<template>
  <ion-app>
    <ion-content>
      <div class="ion-activatable ripple-parent">
        A plain div with a bounded ripple effect
        <ion-ripple-effect></ion-ripple-effect>
      </div>

      <button class="ion-activatable ripple-parent">
        A button with a bounded ripple effect
        <ion-ripple-effect></ion-ripple-effect>
      </button>

      <div class="ion-activatable ripple-parent">
        A plain div with an unbounded ripple effect
        <ion-ripple-effect type="unbounded"></ion-ripple-effect>
      </div>

      <button class="ion-activatable ripple-parent">
        A button with an unbounded ripple effect
        <ion-ripple-effect type="unbounded"></ion-ripple-effect>
      </button>
    </ion-content>
  </ion-app>
</template>

<style>
  .ripple-parent {
    position: relative;
    overflow: hidden;
  }
</style>

<script>
import { IonApp, IonContent, IonRippleEffect } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonApp, IonContent, IonRippleEffect }
});
</script>
```

</TabItem>

</Tabs>

## Properties


### type

| | |
| --- | --- |
| **Description** | Sets the type of ripple-effect:<br /><br />- `bounded`: the ripple effect expands from the user's click position<br />- `unbounded`: the ripple effect expands from the center of the button and overflows the container.<br /><br />NOTE: Surfaces for bounded ripples should have the overflow property set to hidden,<br />while surfaces for unbounded ripples should have it set to visible. |
| **Attribute** | `type` |
| **Type** | `"bounded" \| "unbounded"` |
| **Default** | `'bounded'` |



## Methods


### addRipple

| | |
| --- | --- |
| **Description** | Adds the ripple effect to the parent element. |
| **Signature** | `addRipple(x: number, y: number) => Promise<() => void>` |

