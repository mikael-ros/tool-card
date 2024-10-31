> [!WARNING]
> This project is deprecated. I refer you to [profile-card](https://www.github.com/mikael-ros/profile-card) instead.

---

# 🔨 GitHub Tool Card
![](./tool-card.svg)

This is a profile card made in a SVG, that can be imported into a GitHub profile readme (or elsewhere). It works by using a ``foreignObject`` inside of an SVG, which allows you to use HTML and CSS beyond what the GitHub sanitization process allows.

This is based on my other profile project, [GitHub Language Card](https://github.com/mikael-ros/profile-card). The main difference is the layout, which here is designed to be wider and more accomodating, since tools are likely to be a longer list.

---

## 🔨 Usage
To use the card, either copy the contents of [``tool-card.svg``](./tool-card.svg) or download it. Then paste it into your profile git repository, and add an image tag in your profile readme, displaying the SVG, like this: ``![](path/to/tool-card.svg)``. The path can also be to the raw file, if hosted in a seperate repository.

### 🪚 How to modify
Simply go into the SVG and add entries accordingly. There are 6 proficiencies, all identified by ids; see the SVG as an example.

> [!TIP]
> When editing the SVG, open the file locally in the browser. It is a more accurate preview of how it will look in the real world.

#### 📁 Card
The entire thing is contained within an ``<article>`` tag, which is necessary to make it display properly on all GitHub themes. See the minimal example further down.

#### ⌨️ Typing animation
The typing animation is **implemented with keyframes**, changing the content each keyframe. You can with some effort change this text. _If your text is the same length or shorter you can get away with less editing._

> [!TIP]
> Divide 100% by the amount of letters you want to type and increment the keyframe by that. You can experiment a lot with this though.
> Also see [this code example](https://codepen.io/alvaromontoro/pen/rNwVpdd) if you want to change the type of typing marker. Default is ``_``.

#### 🗂 Categories
Every category is contained in it's own ``<section class="category-container"``, containing a ``<h4>`` element and an ``<ul>`` element.

```html
<section class="category-container">
    <h4><span class="emoji">🔵</span> Category</h4>
    <ul>
        <li class="proficient">🦝 Racoon Tool</li>
        <li class="learning">💅 Girlboss</li>
    </ul>
</section>
```

##### 🗃️ Nested categories
You can also nest categories, by putting an ``<ul>`` inside of one of the ``<li>``. This works infinitely, though I wouldn't reccomend it. You can both color the whole ``<ul>`` the same color and have specific elements be a certain color.
```html
<section class="category-container">
    <h4><span class="emoji">🔵</span> Category</h4>
    <ul>
        <li class="proficient"> 🦝 Racoon Tools
            <ul>
                <li> 😋 Silly </li>
                <li> 🍇 Grapes </li>
            </ul>
        </li>
    </ul>
</section>
```
To make it display in a vertical column, add the class ``vertical`` to the inner ``<ul>`` element. This simply sets the ``flex-direction`` property to ``column``.

##### 😜 Emojis/icons
Either put the emoji inline, in the ``<h4>`` tag or put it inside ``<span class="emoji">😎</span>``. The ``emoji`` class will make it into it's own little "bubble".

_Unfortunately it's not trivial to include any old icon (you have to convert it into BASE64) which is why I've opted for emojis._

#### 💼 Proficiencies
There are 6 levels built-in. They are as follows:
- 💪 ``proficient``: Tools you can use with your **eyes (almost) closed**
- 👍 ``good``: Tools you know well
- 👌 ``average``: Tools you are average in, **about as competent as most people**
- 🤏 ``below average``: You aren't fully comfortable in this tool, but **you can hack something together with it given some effort**
- 💡 ``accquainted``: You have come across and had to use this tool as part of a course or job, but didn't get the hang of it. Despite, **you can still use it for basic things**
- 🧠 ``learning``: What it **says on the tin**

These are marked by wrapping the corresponding skill in an ``<li>`` element with the class set to one of the above, like:
```html
<li class="proficient">🦝 Racoon Tool</li>
```
Though you can put this class on any element, as it just changes the ``background-color`` property.
##### 🖌 Colors
There are 6 colors corresponding to the 6 proficiencies, which you can change easily by editing CSS variables at the top of the SVG. 

### 🗒 Minimal example
> [!NOTE]
> This does not include the rest of the SVG, you also need the headings and style. See the SVG file.
```html
<article id="language-card">
    <section class="category-container">
        <h4><span class="emoji">🔵</span> Category</h4>
        <ul>
            <li class="proficient">🦝 Racoon.js</li>
            <li class="learning">💅 Girlboss</li>
        </ul>
    </section>

    <section class="category-container" id="legend">
        <h4><span class="emoji">🗺️</span> Legend</h4>
        <ul>
            <li class="proficient">💪 Proficient</li>
            <li class="good">👍 Good</li>
            <li class="average">👌 Average</li>
            <li class="belowaverage">🤏 Below average</li>
            <li class="accquainted">💡 Accquainted</li>
            <li class="learning">🧠 Learning</li>
        </ul>
    </section>
</article>
```

> [!TIP]
> Don't forget to change the SVG height and width at the top of the file, or it might either be too large or get cut off. Also set the ``language-card`` height.

---

## 👥️ Contributing

Feel free to contribute, though I would prefer you not change the contents of the list in this repository as the SVG hosted here is used on my profile.

---

## 👋 Attributing

While it is not necessary, **I would be happy if you referred** to this repo when using the card. I would also love to see what you create with it!

> [!IMPORTANT]
> This repository is licensed under the [MIT license](LICENSE), please accquaint yourself with it before using this code.

---

## 🫡 Acknowledgements
> [!IMPORTANT]
> While making the typing animation, I used [this CSS animation](https://codepen.io/alvaromontoro/pen/rNwVpdd) and [this guide](https://css-tricks.com/snippets/css/typewriter-effect/), for reference - though it has since strayed from those roots. Otherwise **everything else is my own work.** 

---
> This repository is updated in conjunction with my profile, mainly so it is easier to maintain. Not every commit is therefore relevant functionality - some are simply me updating my profile.
