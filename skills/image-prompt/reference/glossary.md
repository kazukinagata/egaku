# image-prompt vocabulary

Curated map from everyday language to the professional terms image generators
respond to. Use it three ways: offer the **Plain cue** options during the
interview, name the **Pro term** when you confirm (the teaching layer), and drop
the **In-prompt phrasing** into the final English prompt.

This file is intentionally selective — it covers what amateurs most often want,
not every term. Pro terms are in English (most controllable for the models);
generate the plain-language version and the answer options in the *user's*
language at runtime.

## Contents

1. Purpose → settings (aspect ratio & framing)
2. Composition & framing
3. Camera angle & distance
4. Lens & focus
5. Lighting
6. Color & mood
7. Style / medium
8. Texture, material & finish
9. Design styles (graphic / UI)
10. Quality & detail

---

## 1. Purpose → settings

Infer these from "what's it for?" instead of asking aspect ratio directly.

| Use | Aspect ratio | Notes |
| --- | --- | --- |
| Social avatar / profile icon | 1:1 | Centered subject, simple background |
| Instagram post | 1:1 or 4:5 | 4:5 fills more feed space |
| Story / Reel / TikTok / phone wallpaper | 9:16 | Vertical, leave headroom for UI |
| Blog header / hero / banner | 16:9 or 3:1 | Wide; keep space for overlaid text |
| YouTube thumbnail | 16:9 | Bold, high-contrast, readable small |
| Poster / flyer | 2:3 or 3:4 | Portrait; room for a title block |
| Slide / doc illustration | 16:9 or 4:3 | Clean, uncluttered |
| Desktop wallpaper | 16:9 or 16:10 | Subject off-center for icons |
| Print / large format | match output | Ask the physical proportions |

Purpose also hints at **polish** (icons & posters → clean and bold; "just for
fun" → looser) and **register** (corporate → restrained palette; personal → freer).

## 2. Composition & framing

| Pro term | Effect / when to use | Plain cue (offer as option) | In-prompt phrasing |
| --- | --- | --- | --- |
| Rule of thirds | Natural, balanced placement | "Subject a bit off to the side?" | "composed using the rule of thirds" |
| Centered / symmetrical | Bold, iconic, calm | "Subject dead center?" | "centered, symmetrical composition" |
| Negative space | Room for text; minimal, airy | "Lots of empty space around it?" | "generous negative space around the subject" |
| Leading lines | Draws the eye to the subject | "Lines pointing toward the subject?" | "leading lines guiding toward the subject" |
| Framing (in-frame) | Depth; focuses attention | "Seen through a window/arch/foliage?" | "framed through <element> in the foreground" |
| Fill the frame | Impact, intimacy | "Subject filling the whole image?" | "subject filling the frame" |

## 3. Camera angle & distance

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Eye-level | Neutral, relatable | "Straight-on, normal height?" | "eye-level shot" |
| Low angle | Makes subject powerful, tall | "Looking up at it?" | "low-angle shot looking up" |
| High angle | Makes subject small, cute, vulnerable | "Looking down at it?" | "high-angle shot looking down" |
| Top-down / flat lay | Products, food, layouts | "Straight down from above?" | "top-down flat-lay view" |
| Close-up | Emotion, detail | "Tight on the face/detail?" | "close-up shot" |
| Medium shot | Balanced; person + some context | "Head-and-shoulders / waist-up?" | "medium shot, waist-up" |
| Wide / establishing | Show the whole scene | "Pulled back to show everything?" | "wide establishing shot" |
| Macro | Extreme tiny detail | "Super zoomed-in texture?" | "macro shot, extreme detail" |

## 4. Lens & focus

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Shallow depth of field / bokeh | Subject pops, background melts | "Background soft and blurry?" | "shallow depth of field, soft bokeh background" |
| Deep depth of field | Everything sharp (landscapes, products) | "Everything in focus front to back?" | "deep depth of field, everything in sharp focus" |
| Wide-angle lens | Expansive, slight exaggeration | "Big sweeping view?" | "wide-angle lens" |
| Telephoto / compression | Flattering portraits, compressed depth | "Zoomed-in, flattened look?" | "telephoto lens, compressed perspective" |
| Fisheye | Playful, extreme curve | "Curvy, bulging view?" | "fisheye lens distortion" |
| Tilt-shift | Miniature / toy-like | "Looks like a tiny model?" | "tilt-shift, miniature effect" |
| Motion blur | Sense of speed | "Movement streaked/blurred?" | "motion blur conveying movement" |

## 5. Lighting

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Soft / diffused light | Gentle, flattering, few harsh shadows | "Soft, even light?" | "soft diffused lighting" |
| Hard light | Crisp, dramatic shadows | "Strong, sharp shadows?" | "hard directional lighting, defined shadows" |
| Golden hour | Warm, cinematic, flattering | "Warm sunset glow?" | "warm golden-hour light" |
| Backlight / rim light | Glowing outline, separation | "Lit from behind, glowing edges?" | "backlit with a bright rim light" |
| Studio lighting | Clean product / portrait | "Clean studio look?" | "professional studio lighting" |
| Natural window light | Cozy, realistic interiors | "Soft daylight from a window?" | "soft natural window light" |
| Neon / practical lights | Night, urban, moody | "Colorful neon glow?" | "moody neon lighting" |
| High-key | Bright, airy, minimal shadow | "Bright and cheerful, almost white?" | "high-key lighting" |
| Low-key / chiaroscuro | Dark, dramatic, mysterious | "Mostly dark with pools of light?" | "low-key chiaroscuro lighting" |
| Volumetric / god rays | Visible light beams, atmosphere | "Beams of light through haze?" | "volumetric light, visible god rays" |

## 6. Color & mood

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Warm palette | Cozy, energetic, inviting | "Reds/oranges/yellows?" | "warm color palette" |
| Cool palette | Calm, clean, techy | "Blues/greens/purples?" | "cool color palette" |
| Muted / desaturated | Subtle, sophisticated, vintage | "Soft, faded colors?" | "muted, desaturated tones" |
| Vibrant / saturated | Punchy, playful, eye-catching | "Bold, vivid colors?" | "vibrant, saturated colors" |
| Monochromatic | Elegant, unified | "All shades of one color?" | "monochromatic <color> palette" |
| Pastel | Soft, sweet, gentle | "Light, candy-like colors?" | "soft pastel palette" |
| Complementary contrast | Dynamic, high impact | "Two opposite colors popping?" | "complementary color contrast (<a> vs <b>)" |
| Earth tones | Organic, natural, grounded | "Browns, greens, sand?" | "natural earth-tone palette" |

Mood words that read well in prompts: serene, cozy, dramatic, dreamy, energetic,
melancholic, whimsical, futuristic, nostalgic, minimalist.

## 7. Style / medium

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Photorealistic | Looks like a real photo | "Like a real photograph?" | "photorealistic, high detail" |
| Cinematic still | Film-like, graded, dramatic | "Looks like a movie scene?" | "cinematic film still, color-graded" |
| Anime / manga | Japanese animation look | "Anime style?" | "anime style, clean line art, cel shading" |
| Watercolor | Soft, bleedy, handmade | "Watercolor painting?" | "watercolor painting, soft washes" |
| Oil painting | Rich, textured, classic | "Oil painting, visible brushwork?" | "oil painting, visible brushstrokes" |
| Flat vector illustration | Clean, modern, scalable | "Simple flat illustration?" | "flat vector illustration, clean shapes" |
| 3D render | Polished CGI, depth | "3D rendered look?" | "3D render, soft global illumination" |
| Isometric | Diagrams, games, cute scenes | "Tilted 3D blocks view?" | "isometric illustration" |
| Pixel art | Retro game look | "Retro pixel art?" | "pixel art, limited palette" |
| Line art / sketch | Minimal, editorial | "Just clean line drawing?" | "minimal line art on white" |
| Claymation / 3D clay | Soft, tactile, friendly | "Looks like clay figures?" | "claymation style, soft clay texture" |

## 8. Texture, material & finish

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Matte finish | Soft, non-reflective | "Flat, no shine?" | "matte finish" |
| Glossy / specular | Shiny, premium, wet | "Shiny and reflective?" | "glossy surface with specular highlights" |
| Metallic | Chrome, gold, premium | "Metal/chrome/gold?" | "polished metallic surface" |
| Translucent / frosted | Soft glow-through | "See-through, frosted?" | "translucent frosted material" |
| Grain / film texture | Analog, organic feel | "Slight grainy/film texture?" | "subtle film grain" |
| Rough / organic texture | Tactile, natural | "Rough, hand-made texture?" | "rough organic texture" |

## 9. Design styles (graphic / UI)

For logos, icons, UI mockups, posters, and graphic compositions.

| Pro term | Effect / when to use | Plain cue | In-prompt phrasing |
| --- | --- | --- | --- |
| Glassmorphism | Frosted-glass cards, depth, modern UI | "Frosted-glass, see-through panels?" | "glassmorphism, frosted translucent panels with blur" |
| Neumorphism | Soft extruded UI, subtle shadows | "Soft buttons that look pressed in/out?" | "neumorphic soft UI, subtle inner/outer shadows" |
| Flat design | Simple, no gradients/shadows | "Plain and flat, no shadows?" | "flat design, solid colors" |
| Material design | Layered, shadowed, Google-like | "Layered cards with shadows?" | "material design, elevation shadows" |
| Brutalism | Raw, bold, high-contrast | "Raw, bold, in-your-face?" | "brutalist design, bold blocky type" |
| Minimalist | Lots of space, few elements | "Clean and minimal?" | "minimalist, lots of white space" |
| Retro / vintage | Nostalgic era look | "Old-school / retro vibe?" | "retro <era> aesthetic" |
| Gradient / aurora mesh | Smooth colorful blends | "Smooth colorful gradient background?" | "smooth gradient mesh background" |
| Line / outline icon | Simple iconography | "Simple outline icon?" | "outline icon style, consistent stroke width" |

## 10. Quality & detail

Light touches that lift results — use sparingly, don't stack clichés.

| Pro term | When | In-prompt phrasing |
| --- | --- | --- |
| High detail | Most images | "highly detailed" |
| Sharp focus | Photoreal subjects | "sharp focus on the subject" |
| Professional / award-winning | Hero shots | "professional, polished result" |
| Clean composition | Icons, products, UI | "clean, uncluttered composition" |

Avoid piling on empty quality words ("8k, ultra, masterpiece, trending") — one or
two purposeful detail cues beat a long stack.
