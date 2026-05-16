**REFLECTION A6**

Looking at the misclassified samples, the CNN appears to struggle most with tops. Specifically confusing T-shirts, Shirts, Pullovers, Dresses, and Coats with one another. This is unsurprising visually. A boxy white T-shirt and a collared shirt are nearly indistinguishable.

Fine details like buttons, collars, and hemlines collapse into noise at this resolution. The model also confuses coats with pullovers and trousers, likely because long, light-coloured garments share the same
silhouette when flattened to low-res grayscale.

To fix this for production, the highest impact change would be higher-resolution colour images. Colour alone would separate many of these (e.g., fabric texture, print patterns), and more pixels would preserve
structural details like necklines and sleeve cuts that the model currently can't see.


**REFLECTION B6**

The persona breaks most reliable in open-ended and factual questions. It often ends up in a loop or hallucinating and doesn't really stick to its persona be it the way it talks or what it talks about. It starts sounding generic in these areas instead of bringing the conversation back to dogs like its supposed to. 

Adding more details to the prompt would help. eg. 'Dont repeat phrases'. But it would not fix the problem entirely. 

Ultimately the model is too small. I would reach for GPT-4 or Claude when I require more skillful answers and when I need it to hold up a long conversation.
