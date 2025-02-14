
<a href="https://github.com/Jumman04/Jummania-Slider"></a>

<h1 align="center">J-Slider for Android!</h1>  
<a href="https://github.com/Jumman04/Jummania-Slider">  
<img align="left" src="https://github-production-user-asset-6210df.s3.amazonaws.com/113237846/284076921-b31614c3-e3cb-40a6-ab4b-31c9b9517dda.gif"  />  </a>  

<li>Easy to use.</li>
<li>Smooth sliding transitions.</li>
<li>Customizable indicator size, colors, and shapes.</li>
<li>Auto-sliding functionality.</li>
<li>Slide with a variety of 38+ different animations.</li>
<li>Ability to add your own custom animation.</li>
<li>Indicator alignment and gravity customization.</li>
<li>Use with Java or Kotlin.</li>
<br>
<p align="left">
	<img src="https://img.shields.io/badge/API-17%2B-brightgreen.svg?style=flat"/>
	<img src="https://img.shields.io/github/v/release/Jumman04/Jummania-Slider?include_prereleases&amp;label=latest%20release" alt="Latest release"/>
	 <a href="https://jitpack.io/#Jumman04/Jummania-Slider">
    <img src="https://jitpack.io/v/Jumman04/Jummania-Slider.svg"/> </a>

  <a href="https://github.com/Jumman04/Jummania-Slider/issues">
    <img src="https://img.shields.io/github/issues/Jumman04/Jummania-Slider"/>
  </a>
 <a href="https://github.com/Jumman04/Jummania-Slider/graphs/contributors" >
        <img src="https://img.shields.io/github/contributors/Jumman04/Jummania-Slider" /></a>
    <a href="https://github.com/Jumman04/Jummania-Slider/pulse" >
        <img src="https://img.shields.io/github/commit-activity/m/Jumman04/Jummania-Slider" /></a>

  <a href="https://github.com/Jumman04/Jummania-Slider/network/members">
    <img src="https://img.shields.io/github/forks/Jumman04/Jummania-Slider"/>
  </a>
  <a href="https://github.com/Jumman04/Jummania-Slider/stargazers">
    <img src="https://img.shields.io/github/stars/Jumman04/Jummania-Slider"/>
  </a>
    <a href="https://github.com/Jumman04/Jummania-Slider/LICENSE">
    <img src="https://img.shields.io/github/license/Jumman04/Jummania-Slider"/></a>
</p>
<br>


---

<details>
  <summary><h1>Setup</h1></summary>
  <br>

To integrate Jummania-Slider into your Android project, follow these steps:

### Step 1: Add JitPack Repository

Add the JitPack repository to your project's root `settings.gradle` file:

```groovy
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

## Step 2: Add the Dependency

Add the Jummania-Slider dependency to your app module's `build.gradle` file:

---

<details>
  <summary>For Kotlin</summary>
  <br>

  ```gradle
dependencies {
    implementation 'com.github.Jumman04:Jummania-Slider:3.6'
}
```
  </details>
  
---

<details>
  <summary>For Java</summary>
  <br>

  ```gradle
dependencies {
    implementation 'com.github.Jumman04:Jummania-Slider:3.5'
}
```
### Note for Java Developers:
Our latest library may not be fully compatible with Java. You can still use it, but be aware of potential issues.

  </details>


 </details>

 ---
 <details>
  <summary><h1>Usage</h1></summary>

---

<details>
  <summary>XML</summary>
  <br>

```xml

    <com.jummania.JSlider 
        android:id="@+id/jSlider" 
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />
```
</details>

---

<details>
  <summary>For Kotlin</summary>
  <br>

```kt
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    val jSlider: JSlider = findViewById(R.id.jSlider)
    jSlider.setSlider(DefaultSlider())

}

//Out of onCreate, Create a Class for Slider
private inner class DefaultSlider : JSlider.DefaultSlider() {
    override fun getView(layoutInflater: LayoutInflater, parent: ViewGroup): View {
        return layoutInflater.inflate(R.layout.item_slider2, parent, false) //Inflate you layout
    }

    override fun onSliderCreate(view: View, position: Int) {

        val textView: TextView = view.findViewById(R.id.text_view) //find your child
        val imageView: ImageView = view.findViewById(R.id.image_view)

        Picasso.get()
            .load("https://jummania.com/App/BanglaNatokSamahar/Images/Cover%20Photo.jpg")
            .error(R.drawable.default_error).placeholder(R.drawable.default_loading)
            .into(imageView)

        textView.text = getString(R.string.Developer_Name)

        view.setOnClickListener {
            //Apply your click Listener
        }


    }

    override fun getCount(): Int {
        return 3
    }

}
```
</details>

---

<details>
  <summary>For Java</summary>
  <br>

 ```Java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        JSlider jSlider = findViewById(R.id.jSlider);
        jSlider.setSlider(new DefaultSlider());
    }

    private class DefaultSlider extends JSlider.DefaultSlider {
        @Override
        public View getView(LayoutInflater layoutInflater, ViewGroup parent) {
            return layoutInflater.inflate(R.layout.item_slider2, parent, false);
        }

        @Override
        public void onSliderCreate(View view, int position) {
            TextView textView = view.findViewById(R.id.text_view);
            ImageView imageView = view.findViewById(R.id.image_view);

            Picasso.get()
                    .load("https://jummania.com/App/BanglaNatokSamahar/Images/Cover%20Photo.jpg")
                    .error(R.drawable.default_error)
                    .placeholder(R.drawable.default_loading)
                    .into(imageView);

            textView.setText(getString(R.string.Developer_Name));

            view.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    // Apply your click listener logic
                }
            });
        }

        @Override
        public int getCount() {
            return 3;
        }
    }
}
```
</details>

</details>

---

<details>
  <summary><h1>Customization</h1></summary>

---

<details>
  <summary>XML Attributes</summary> 
<br>
	
- Change Duration of Sliding:

```xml
app:slidingDuration="2222"
```

- Change Indicator Size:

```xml
app:indicatorSize="15dp"
```

- Add Padding in Slider:

```xml
app:sliderPaddingRight="0dp"
app:sliderPaddingLeft="0dp"
app:sliderPaddingTop="0dp"
app:sliderPaddingBottom="0dp"
```

- Change Indicator Padding:

```xml
app:indicatorPaddingTop="0dp"
app:indicatorPaddingLeft="0dp"
app:indicatorPaddingRight="0dp"
app:indicatorPaddingBottom="22dp"

```

- Change Indicator Margin Horizontal:

```xml
app:indicatorMarginHorizontal="3dp"
```

- Hide or Show Indicator:

```xml
app:enableIndicator="true"
```

- Enable or Disable Auto Sliding:

```xml
app:enableAutoSliding="true"
```

- Change Default Indicator Color:

```xml
app:defaultIndicatorColor="@color/defaultColor"
```

- Change Selected Indicator Color:

```xml
app:selectedIndicatorColor="@color/selectedColor"
```

- Choose How the Indicator Updates:

```xml
app:indicatorUpdateMode="SYNC"
```

- Set the Alignment of the Indicator:

```xml
app:indicatorAlign="ALIGN_BOTTOM"
```

- Specify the Gravity of the Indicator:

```xml
app:indicatorGravity="center"
```

- Set Indicator Shape Type:

```xml
app:shapeTypes="CIRCLE"

    <!-- Choose one of the following options for the shape type: CIRCLE, HEART, SQUARE, or STAR. -->
```

- Set Slide Animation:

```xml
app:slideAnimation="CUBE_OUT"
```

</details>

---



 <details>
  <summary>For Kotlin</summary>
  <br>
 

- Set the sliding duration:

```kt
setSlidingDuration(2222)
```

- Set the indicator size:

```kt
setIndicatorSize(15)
```

- Set the indicator colors:

```kt
setIndicatorColor(defaultColor, selectedColor)
```

- Enable or disable the indicator:

```kt
enableIndicator(true)
```

- Enable or disable auto-sliding:

```kt
enableAutoSliding(true)
```

- Set a custom page transformer:

```kt
setPageTransformer(true, PageTransformer())
```

- Set padding for the slider:

```kt
setSliderPadding(left, top, right, bottom)
```

- Set horizontal margin for the indicator dots:

```kt
setIndicatorMarginHorizontal(3)
```

- To start or stop auto-sliding:

```kt
startAutoSliding()
stopAutoSliding()
```

- Slide to the next and previous page:

```kt
slideNext()
slidePrevious()
```

- Check if the slider is currently sliding:

```kt
isSliding()
```

- Set padding for the indicator dots programmatically:

```kt
setIndicatorPadding(left, top, right, bottom)
```

- Set the gravity for both the dot indicators:

```kt
setIndicatorGravity(Gravity.BOTTOM)
```

- Set the alignment for both the dot indicators:

```kt
setIndicatorAlignment(Alignment.BOTTOM)
```

- Set the indicator update mode:

```kt
setIndicatorUpdateMode(UpdateMode.SYNC)
```

- Set the indicator shape types programmatically:

```kt
setIndicatorShapeTypes(ShapeTypes.CIRCLE)
```

- You can add animation like that, <b>38 Animations added</b>. You can check
  in <a href="https://github.com/Jumman04/Jummania-Slider/blob/master/J-Slider/src/main/java/com/jummania/types/AnimationTypes.kt">
  Animation List </a>

```kt
jSlider.setSlideAnimation(AnimationTypes.ZOOM_OUT)
```

- You can add 'addOnSlideChangeListener' if you really need

```kt
 jSlider.addOnSlideChangeListener(object : JSlider.OnSlideChangeListener {
    override fun onSliderScrolled(
        position: Int, positionOffset: Float, positionOffsetPixels: Int
    ) {
        Log.d(
            "JSlider",
            "position: $position, positionOffset: $positionOffset, positionOffsetPixels: $positionOffsetPixels"
        )
    }

    override fun onSliderSelected(position: Int) {
        Log.d("JSlider", "position: $position")
    }

    override fun onSliderScrollStateChanged(state: Int) {
        Log.d("JSlider", "state: $state")
    }

})
```

- If you want to Reverse-less slide:

```kt
 private inner class InfinitySlider : JSlider.InfinitySlider() {
    override fun itemCount(): Int {
        return 3
    }

    override fun getView(layoutInflater: LayoutInflater, parent: ViewGroup): View {
        return layoutInflater.inflate(R.layout.item_slider2, parent, false) //Inflate you layout
    }

    override fun onSliderCreate(view: View, position: Int) {
        val textView: TextView = view.findViewById(R.id.text_view) //find your child
        val imageView: ImageView = view.findViewById(R.id.image_view)

        Picasso.get()
            .load("https://jummania.com/App/BanglaNatokSamahar/Images/Cover%20Photo.jpg")
            .error(R.drawable.default_error).placeholder(R.drawable.default_loading)
            .into(imageView)

        textView.text = getString(R.string.Developer_Name)

        view.setOnClickListener {

            Toast.makeText(
                this@MainActivity, getString(R.string.Developer_Name), Toast.LENGTH_SHORT
            ).show()
        }
    }

}
```
</details>

---



 <details>
	
  <summary>For Java</summary>
	 <br>

  
- Set the sliding duration:

```kt
setSlidingDuration(2222);
```

- Set the indicator size:

```kt
setIndicatorSize(15);
```

- Set the indicator colors:

```kt
setIndicatorColor(defaultColor, selectedColor);
```

- Enable or disable the indicator:

```kt
enableIndicator(true);
```

- Enable or disable auto-sliding:

```kt
enableAutoSliding(true);
```

- Set a custom page transformer:

```kt
setPageTransformer(true, PageTransformer());
```

- Set padding for the slider:

```kt
setSliderPadding(left, top, right, bottom);
```

- Set horizontal margin for the indicator dots:

```kt
setIndicatorMarginHorizontal(3);
```

- To start or stop auto-sliding:

```kt
startAutoSliding();
stopAutoSliding();
```

- Slide to the next and previous page:

```kt
slideNext();
slidePrevious();
```

- Check if the slider is currently sliding:

```kt
isSliding();
```

- Set padding for the indicator dots programmatically:

```kt
setIndicatorPadding(left, top, right, bottom);
```

- Set the gravity for both the dot indicators:

```kt
setIndicatorGravity(Gravity.BOTTOM);
```

- Set the alignment for both the dot indicators:

```kt
setIndicatorAlignment(Alignment.BOTTOM);
```

- Set the indicator update mode:

```kt
setIndicatorUpdateMode(indicatorUpdateMode.SYNC);
```

- Set the indicator shape types programmatically:

```kt
setIndicatorShapeTypes(indicatorShapeTypes.CIRCLE);
```

- You can add animation like that, <b>38 Animations added</b>. You can check
  in <a href="https://github.com/Jumman04/Jummania-Slider/blob/master/J-Slider/src/main/java/com/jummania/types/AnimationTypes.kt">
  Animation List </a>

```kt
jSlider.setSlideAnimation(AnimationTypes.ZOOM_OUT);
```

- You can add 'addOnSlideChangeListener' if you really need

```Java
jSlider.addOnSlideChangeListener(new JSlider.OnSlideChangeListener() {
    @Override
    public void onSliderScrolled(int position, float positionOffset, int positionOffsetPixels) {
        Log.d("JSlider", "position: " + position + ", positionOffset: " + positionOffset +
                ", positionOffsetPixels: " + positionOffsetPixels);
    }

    @Override
    public void onSliderSelected(int position) {
        Log.d("JSlider", "position: " + position);
    }

    @Override
    public void onSliderScrollStateChanged(int state) {
        Log.d("JSlider", "state: " + state);
    }
});
```

- If you want to Reverse-less slide:

```Java
private class InfinitySlider extends JSlider.InfinitySlider {
    @Override
    public int itemCount() {
        return 3;
    }

    @Override
    public View getView(LayoutInflater layoutInflater, ViewGroup parent) {
        return layoutInflater.inflate(R.layout.item_slider2, parent, false);
    }

    @Override
    public void onSliderCreate(View view, int position) {
        TextView textView = view.findViewById(R.id.text_view);
        ImageView imageView = view.findViewById(R.id.image_view);

        Picasso.get()
                .load("https://jummania.com/App/BanglaNatokSamahar/Images/Cover%20Photo.jpg")
                .error(R.drawable.default_error)
                .placeholder(R.drawable.default_loading)
                .into(imageView);

        textView.setText(getString(R.string.Developer_Name));

        view.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, getString(R.string.Developer_Name),
                        Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```
	 
 </details>
 

</details>

---

<details>
  <summary><h1>Feature Requests</h1></summary>
  <br>

	
If you have a feature request or a suggestion for improving this library, please feel free
to [open an issue](https://github.com/Jumman04/Jummania-Slider/issues/new) and let us know! We
appreciate your feedback and are always looking to make our library better.

#### How to Request a Feature

1. Click on the [Issues tab](https://github.com/Jumman04/Jummania-Slider/issues).
2. Click the green "New Issue" button.
3. Choose the "Feature Request" template.
4. Fill in the requested information and submit the issue.

Thank you for helping us improve the library!
</details>

---


<details>
  <summary><h1>📄 License</h1></summary>
  <br>

	
This project is licensed under the MIT License - see
the [LICENSE.md](https://github.com/Jumman04/Jummania-Slider/blob/master/LICENSE.md) file for
details.
</details>

---

