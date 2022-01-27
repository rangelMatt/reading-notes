# Code 201 Class 14 Reading Notes

## CSS Transforms

CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All these new techniques are made possible by the transform property.

The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.

## 2D Transforms

Elements may be distorted, or transformed, on both a two-dimensional plan or a three-dimensional plan. Two-dimensional transforms work on the `x` and `y` axes, known as horizontal and vertical axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth. We'll start by discussing how to transform elements on a two-dimensional plane, and then work our way into three-dimensional transforms.

### 2D Rotate

The `rotate` value provides the avility to rotate an element from `0` to `360` degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise.

HTML

```json
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS

```json
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

## Transitions & Animations

One evolution with CSS3 was the avility to write behaviors for transitions and animations.

With CSS3 transitions you have the potential to alter the appearance and beheavior of an element whenever a state change occurs, such as when it is hovered over, focused on, active, or targeted.

### **Transitions**

The easiest way for changing an elements state is by using `:hover`, `:focus`, `:active`, and `:target` pseudo-classes.

#### Transitional Property

The `transition-property` property determines exactly what properties will be altered in conjuction with the other transitional properties. By default, all of the properties within an element's different states will be altered upon change. However, only the properties identified within the `transition-property` value will be affected by any transitions.

If multiple properties need to be transitioned they may be comma seperated within the `transition-property` value. The key word value `all` may be used to transition all properties of an element.

##### Transitional Properties

**Not all properties may be transitioned**, only properties that have an identifiable halfway point.

[<---BACK](README.md)
