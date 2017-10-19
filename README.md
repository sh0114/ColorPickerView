# ColorPickerView
You can use like just ImageView and you can get HSV colors, RGB values, Html color codes <br>
from your gallery pictures or custom images just using touch.

![111](https://user-images.githubusercontent.com/24237865/31732307-0bd47b5c-b473-11e7-9f17-d81bc4b59cf4.jpg)
![222](https://user-images.githubusercontent.com/24237865/31732308-0c0892de-b473-11e7-88f4-9c91e02c543e.jpg)

# Multi-ColorPickerView
You can get colors using multi selectors.

![333](https://user-images.githubusercontent.com/24237865/31732309-0c3557b0-b473-11e7-8104-43534a6ca0dc.jpg)

## Including in your project
#### build.gradle
```java
repositories {
  mavenCentral() // or jcenter() works as well
}

dependencies {
  compile 'com.github.skydoves:colorpickerview:1.0.7'
}
```

#### or Maven
```xml
<dependency>
  <groupId>com.github.skydoves</groupId>
  <artifactId>colorpickerview</artifactId>
  <version>1.0.7</version>
</dependency>
```
    
## Usage
You can use like using just ImageView and you can get color from any images.

#### Add XML Namespace
First add below XML Namespace inside your XML layout file.

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
```

#### ColorPickerView in layout
```xml
<com.skydoves.colorpickerview.ColorPickerView
        android:id="@+id/colorPickerView"
        android:layout_width="300dp"
        android:layout_height="300dp"
        app:palette="@drawable/palette"
        app:selector="@drawable/wheel" />
```

#### Attribute description
```
app:palette="@drawable/palette" // set palette image
```

```
app:selector="@drawable/wheel" // set selector image. This isn't required always. If you don't need, don't use.
```

#### Color Selected Listener
```java
colorPickerView.setColorListener(new ColorListener() {
            @Override
            public void onColorSelected(int color) {
                LinearLayout linearLayout = findViewById(R.id.linearLayout);
                linearLayout.setBackgroundColor(color);
            }
        });
```

#### Methods
Methods | Return | Description
--- | --- | ---
getColor() | int | the last selected color
getColorHtml() | String | the last selected Html color code
getColorRGB() | int[3] | the last selected color's RGB value.<br> int[0] : R, int[1] : G, int[2] : B
setPaletteDrawable(Drawable drawable) | void | change palette drawable resource
setSelectorDrawable(Drawable drawable) | void | change selector drawable resource
setSelectorPoint(int x, int y) | void | moving selector at point(x, y)
selectCenter() | void | select center of drawable image

# License
```xml
Copyright 2017 skydoves

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
