Project brief :

In this challenge, you will develop a blog card featuring editorial content, including an article cover image, a content category tag, a title, a brief description, and a call-to-action (CTA) link.

Implementation requirements :

Design fidelity: Aim to follow the design as closely as possible. All elements in the design should be present, using the specified text color, font size, font weight, spacing, dimensions, etc.
Link interactivity: Implement and style links to reflect different states - normal, hover and focus.
Placeholders: You may leave the redirection links empty for any unspecified buttons or links.
Cross-browser compatibility: Check that your solution works for major browsers including Chrome, Firefox and Safari.
[Stretch goal] Performance optimization: Optimize image assets and code for quick load times, ensuring a smooth and responsive user experience.
[Stretch goal] Accessibility and semantics: Follow best practices for web accessibility, such as using semantic HTML and ARIA roles where necessary, using proper alt tags for images and ensuring that buttons can be navigated to and selected using keyboard controls.

Relevant concepts
These CSS concepts will be useful for this challenge.

Box model: Understanding padding, borders, and margins is necessary for achieving the desired layout.
Flex: Flex layouts are useful for adding gaps between a stack of elements. While flex is not the only way to achieve the layout, it is the modern way of doing so.
Images: How to render images where the original image doesn't necessarily fit within the allocated dimensions.
Recommended approach
Build the page layout: Render a background color for the page. Within the page, add a horizontally-centered card that is a fixed distance of 120px from the top of the page.
Build the card and its contents: Display the article image, badge, title, excerpt, and button link.
Card structure
Build the card container first, then add the contents starting from the top.
Use semantic HTML elements to create containers for different parts of the card. For instance, you might have one <div> for the card itself, an <img> tag to display the blog article image, and another <div> for wrapping the textual content.
You can use either an <img> or a <picture> tag to display the blog article image, just be sure to provide alt attributes for accessibility.
Card layout
Observe that the card has a fixed width of 340px and is a fixed distance of 120px from the top of the screen (it is not vertically centered!).

Set a fixed width and margin-top for the card.
The card should not have a hardcoded height value; its height should be according to the vertical space taken up by its contents. This is the behavior by default in CSS, so there are no extra steps needed.
To horizontally center the card on the page, a simple way would be margin-left: auto; margin-right: auto or to make the card parent display: flex; justify-content: center.
Since the the elements within the card are laid out in a vertical direction, there's no need to use display: flex for arranging the card elements. However, do try using display: flex; flex-direction: column and gap for the vertical spacing between the text elements.
Styling the card and its contents
When styling, use classes to apply styles to specific elements as opposed to inline styles. There can be more than one blog card per page, using classes will allow you to apply the styles to another blog card instance.
Notice that the card has a box shadow, a border, a background color and rounded corners! Be sure to add the necessary styling.
Refer to the style guide for the appropriate typography values and colors to use.
Notice that the button link has a custom focus style.
Ensuring cards have the same height
In reality, blog cards are usually displayed in a list, along other blog cards. When they are placed side-by-side, it is more aesthetically pleasing for their contents (image, title, excerpt) to be aligned horizontally (at the same level). At the very least, the cards in a list should be of the same height. In fact, we use these techniques on this very platform to have same-height challenge cards and submission cards.

Let's see how we can achieve this.

Image
Since the image can be of varying dimensions and aspect ratios, we can use a fixed height on the image and have the image fill up the entire allocated space.

Common ways to display the images include using an <img> tag or the background-image CSS property. In the past, developers will lean towards using background-image because of the ability to use background-size: cover, which scales the image (while preserving its ratio) to the smallest possible size to fill the image container, leaving no empty space. These days, <img>s support the object-fit: cover property which achieves a similar effect.

Text elements
The title and excerpt can be longer than one sentence and two sentences respectively. One solution will be to clamp the text to a specific number of lines, using -webkit-line-clamp. Tailwind CSS' Line Clamp utility makes clamping text effortless.

That said, truncation is not ideal because text is being hidden from users. Hence it is recommended to work with article authors to set a guidance on how many characters the title and excerpt should contain.
