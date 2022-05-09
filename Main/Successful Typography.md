#design #typography #web/design
# Successfull Typography
## Features of good typography
- Legibility
- Quick navigability
- Coherence
- Whitespace
- Heirarchical


## Aspects to consider in typography
- Baseline, x-height, ascender, descender, cap-height, x-height:cap-height ratio

![[Pasted image 20220307211421.png|600]]

## Improving legibility
- Ascender should go past cap height, but be reasonable otherwise its too choppy
- Increase leading / letter spacing, and line-height
- [[#Contrast]]
- Serifs can help create distinctive letter shapes to improve legibility
- Short ascender and descenders help by reducing 'choppyness'


## Contrast
- Aim for a 4.5:1 contrast ratio for smaller text
- At least 3:1 for larger text (18px + )
- Color Contrast
- Letter form contrast (varying widths, shapes, etc.)
- Font Weight Contrast 


## Things to Avoid
- Take in to consideration those with [[#Disabilities to consider|disabilities and act accordingly]]
Faux-bold, faux-italic
	- Font designers create different sets to prevent bluriness, and often make other tweaks. Especially italics.
- Floating Heading
	- When space is even above and below a heading makes it hard to determine which body of text it belongs to
	- Suggestion, double spacing on top, single on bottom
- Too much color
	- too much color kills typographic heirarchical flow


## Common practices
- Display fonts have tighter spacing, often all caps
- Monospace should not be used for long paragraphs, it ruins readability after wrapping
- Base font size minimum essentially 16px for ADA
- Set up a [[Typeface CSS Template |type-scale]] sheet to generate heading heights/weights & import into css
- Dont center align text longer than 3ish lines long.
- 45 - 75 characters per line (mid 60s best?)
- When fontsize is large, letter spacing also gets large, reduce letter spacing by 3-5%
- When indenting, typically do 1EM, aka 100% of current font size
	- Don't indent first ling of first paragraph,  after a heading,  after image/figure
- An alternative option to intra paragraph margin is indention of first line of subsequent paragraphs
- When using a block quote with big curly quotes, use negative margin to make lines of text align properly

## Disabilities to consider
- Dyslexia
	- Avoid fully adjusting text
	- Enable hyphenation for fully-adjusted text
- Blurry vision
	- Consider easily adjustable text size for user
- Blind
	- Consider aira-labels, role attributes, screen readers, etc.
- Epilepsy
	- Consider no flashing animation
- Color blindness.   (e.g. red-green, blue-yellow)
	- Adjust color scheme
	- Consider tool to preview in those modes to verify/validate colors

## Typeface Pairing
- Pair typefaces w similar proportions

## Icons
48 x 48 px min

## Small Screens
- Bigger text
- Smaller headings
- tighter leading

## Vertical Rythm
- Using a grid overlway when designing helps determine vertical rythm
- Using multiples of the 1EM * line-height often works best.
- Get Text to align baselines along the grid
- 


<iframe width="720" height="480" src="https://www.youtube.com/embed/agbh1wbfJt8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>