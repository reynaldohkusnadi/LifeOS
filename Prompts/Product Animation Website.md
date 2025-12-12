---
type: prompt
category: Website
tags:
  - prompt
  - ai
created: 2025-12-03
modified: 2025-12-03
model:
status:
effectiveness:
---

# ✍️ Product Animation Website

## Purpose
Transform a singular product image into a high quality animation for website hero page. 
Uses google whisk to generate first and last frame then uses Google Flow to animate. 
Uses "WebP" format to convert .mp4 generated to be inputed to a website


## The Prompt

```
**

1. Nanobanana First Frame Image
    

Create a high-quality product image using the uploaded product photo.

Place the product floating in the center of the frame with a slight natural tilt, similar to commercial beverage ads.

Use clean, soft studio lighting with subtle highlights and shadows to make the product look glossy and premium.

Keep all original label details sharp and readable.

STYLE:

• Same aesthetic as modern DTC beverage ads

• Simple, minimal, flat background

• Clean color separation

• Slight vignette but no gradients

BACKGROUND:

• Pure solid black (#000000)

• No reflections, no textures

FRAMING:

• Full vertical frame

• Product centered

• Enough margins for later motion-tracking

OUTPUT:

• High-resolution still image

• Black background for easy masking

• Maintain the exact shape, colors, and proportions of the user-uploaded product image.

**

**

2. Nanobanana Last Frame Image
    

Using the uploaded product image, generate the final frame of a product animation.

The product should appear floating and tilted slightly forward, while multiple [ingredient] elements burst dynamically around it.

  

INGREDIENT BURST:

• Surround the product with floating [ingredient] pieces arranged in a dynamic outward explosion

• Include a high-energy liquid splash made from the product’s flavor, wrapping partially around the can

• Ingredients should look as if captured in high-speed photography: sharp, crisp, mid-air

• Keep the product label visible and unobstructed

  

STYLE:

• Clean, soft commercial studio lighting

• Bright highlights on the can’s metallic rim

• Sharp ingredient details, no motion blur

• Energetic composition similar to beverage advertising key visuals

  

PRODUCT POSITION:

• Center of the frame

• Slight forward tilt for a dynamic, hero-shot angle

• Ingredients positioned around the product with natural spacing for animation

  

BACKGROUND:

• Pure solid black (#000000)

• No gradients, textures, fog, or shadows

• Designed for clean masking and compositing in video

  

OUTPUT:

• High-resolution final frame

• Product centered with bursting [ingredient] effects

• Completely black background

• Preserve the exact colors and proportions of the uploaded product image.

  

[ingredient]: 

  

3. Transition Prompt:
    

Create a dynamic transition from the mid-spin frame to the final ingredient-burst frame using the uploaded product image.

Begin with the product tilted left in mid-rotation on a pure black background.

As the rotation continues, introduce [ingredient] pieces gradually entering the frame from behind and around the product.

Increase the number of floating [ingredient] elements as the motion progresses, building toward a full ingredient burst.

Add a high-energy liquid splash emerging from behind the product and wrapping partially around it as the ingredients appear.

All elements must look sharp and suspended in high-speed motion.

Ensure the product stays well-lit, well-centered, and unobstructed.

Background stays pure solid black (#000000) with no additional effects.

End the transition in the fully exploded ingredient-burst composition.

  

[ingredient]: 

  

4. Video to Webp (30FPS):
    

- https://ezgif.com/video-to-webp
    

  

5. Website Prompt:
    

Design a premium, single-page parallax website for a canned drink brand.

The user must be able to change:

  

Drink name (e.g. “Coca Cola”)

Drink description (1–3 sentences)

Theme color (brand accent)

Dark or light mode

Multiple WebP background parallax image sequences (one sequence per drink variant)

  

Hero Layout & Visual Style

Create a full-screen hero section with this layout:

  

Background:

- The entire hero background is a WebP image sequence that fills the screen.
    
- As the user scrolls down, the sequence plays forward; scrolling up reverses it.
    
- This animation should feel cinematic and smooth.
    

  

Overlay Text Block (Left Side):

- Below the logo: Large, bold, uppercase drink name (e.g. “CHERRY”).
    
- Under the name: smaller subtitle line, light font weight (e.g. “COLA”).
    
- Under the subtitle: a short descriptive paragraph.
    
- Below the paragraph: two full rounded CTA buttons side by side (e.g. “ADD TO” and “CART”), left one is transparent background and white text color, right one is right background with black text
    
- All of this text overlays directly on top of the moving background.
    

  

Center Area:

- Keep the center visually clean and mostly empty of additional UI, so the animated background is clearly visible behind the text.
    

  

Right Side Variant Navigation:

- On the right, vertically centered, display a huge number representing the current flavor index (01, 02, 03…).
    
- Beside or near that number, include a slim vertical navigation strip with:
    
- A small “PREV” label and arrow for the previous flavor.
    
- A thin vertical divider line.
    
- A small “NEXT” label and arrow for the next flavor.
    
- Clicking PREV/NEXT switches drink variant (text, theme color, and WebP sequence).
    

  

Bottom Center:

- A small row of social icons (Twitter/X, Instagram, Facebook, etc.), minimal and monochrome.
    

  

Theme & Mode:

- Default to a dark, cinematic look: near-black background, bright text.
    
- Provide a toggle for dark/light mode:
    
- Dark: black/charcoal background, white/gray text.
    
- Light: off-white background, dark text.
    
- Apply the theme color to CTAs, accents, active indicators, and subtle highlights.
    

  

Parallax Scroll Behavior

- Map scroll position to the frame index of the WebP sequence:
    
- Scrolling down advances frames.
    
- Scrolling up reverses frames.
    
- The animation should feel tied to the page scroll, not just time-based autoplay.
    
- Keep performance smooth and responsive.
    

  

Multiple Drink Variants

- Support an array of drink variants, where each variant has:
    
- Name
    
- Subtitle
    
- Description
    
- Theme color
    
- Mode (optional override for dark/light)
    
- Path or list of URLs for its WebP frame sequence
    

  

When the user clicks PREV/NEXT:

- Update the hero overlay text to the new drink’s name/subtitle/description.
    
- Update the text with a fade out fade in animation
    
- Change the theme color and mode if specified.
    
- Swap to the corresponding WebP background sequence.
    
- Update the large index number (01, 02, 03…).
    

  

Loading Experience

- Because the site uses WebP sequences:
    
- Before showing the hero, display a full-screen loading overlay with:
    

  

Brand logo or name.

- A horizontal loading bar that fills as frames are loaded.
    
- Optional percentage indicator (e.g. “Loading 72%”).
    
- Only reveal the hero after the initial sequence is fully preloaded to avoid flicker.
    
- When switching variants, show a small loading indicator near the PREV/NEXT controls while the new sequence loads.
    

  

Navigation & Sections

- Create a sticky top navigation bar:
    
- Left: brand logo/name.
    
- Right: links that smooth-scroll to the main sections: Product, Ingredients, Nutrition, Reviews, FAQ, Contact
    
- Indicate the active section while scrolling.
    
- Include the dark/light mode toggle in the navbar.
    

  

Below the hero, design standard sections for a drink website:

- Product / About the Drink – brand story and flavor overview.
    
- Ingredients & Benefits – ingredients list and short benefits.
    
- Nutrition Facts – card styled similar to a nutrition label.
    
- Reviews / Social Proof – testimonials and ratings.
    
- FAQ – accordion Q&A.
    
- Final Call-to-Action – strong headline, CTA buttons, and supporting text.
    
- Footer
    

  

Add a clean footer containing:

- Brand logo or name.
    
- Links (About, Contact, Privacy Policy, Terms).
    
- Social icons.
    
- Copyright text.
    
- Make it visually consistent with the overall theme.
    
- Black background
    

  

In short:

- Generate a cinematic, scroll-controlled parallax drink website where the hero background is a WebP animation tied to scroll, the text overlays directly on top of that animation, the center remains visually open to showcase motion, users can switch between multiple drink flavors via a right-side PREV/NEXT control, and all key content (text, theme, mode, sequences) is easily customizable.
    

  

Company Name: Olipop

Company Description: A modern functional soda brand inspired by classic flavors but made with better ingredients.

Website Theme: Dark Mode Only

Theme Color: Black and White

  

Drink Variant 1

Drink Name: Cherry

Drink Subtitle: Soda

Drink Description: A modern take on a classic soda with a perfect blend of sweet and tart, full of nostalgic flavor.  
WebP Sequence Path URL: https://omqaodalyvzbrvckcumi.supabase.co/storage/v1/object/public/assets/soda/frame_0001.webp

Frame Count: 240  
  

Drink Variant 2

Drink Name: Grape

Drink Subtitle: Soda

Drink Description: A modern functional soda brand inspired by classic flavors but made with better ingredients.

WebP Sequence Path URL: https://omqaodalyvzbrvckcumi.supabase.co/storage/v1/object/public/assets/soda2/frame_0001.webp

Frame Count: 240

  

Drink Variant 3

Drink Name: Lemon

Drink Subtitle: Ginger Soda

Drink Description: Bright and refreshing citrus soda with natural lemon spark and crisp bubbles.  
WebP Sequence Path URL:  
https://omqaodalyvzbrvckcumi.supabase.co/storage/v1/object/public/assets/soda3/frame_0001.webp

Frame Count: 240

  

Placeholder:

[https://placehold.co/1920x1080/frame_0001/FFFFFF/webp](https://placehold.co/1920x1080/frame_0001/FFFFFF/webp)

  

5. CTA Images
    

Create a square CTA product image of the Andy Grape Soda can in the same style as the reference:  
A bold monochrome purple background, smooth studio gradient, clean and minimal.  
Place the Grape Soda can centered and upright, with crisp studio lighting and soft shadow.  
Surround the bottom of the can with realistic, glossy grapes piled across the width, similar to how raspberries appear in the reference.  
Use a vibrant, pop-art aesthetic: bright colors, high contrast, slightly reflective can surface, clean edges.  
No Memphis patterns — keep it simple, bold, color-blocked, just like the reference.  
Overall mood: playful, modern, vibrant, clean.**


```

## Variables/Parameters
- **[Variable 1]:** Description
- **[Variable 2]:** Description

## Example Usage

**Input:**
```

```

**Output:**
```

```

## Effectiveness
- **Rating:** ⭐⭐⭐⭐⭐ (0-5 stars)
- **Works best with:** 
- **Limitations:** 

## Iterations & Improvements

### Version History
- **v1.0** (2025-12-03): Initial version

## Related Prompts
- 
- 

## Notes


---
*Created: 2025-12-03 18:59*
