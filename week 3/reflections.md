**REFLECTION A6**

Looking at the misclassified samples, the CNN appears to struggle most with tops. Specifically confusing T-shirts, Shirts, Pullovers, Dresses, and Coats with one another. This is unsurprising visually. A boxy white T-shirt and a collared shirt are nearly indistinguishable.

Fine details like buttons, collars, and hemlines collapse into noise at this resolution. The model also confuses coats with pullovers and trousers, likely because long, light-coloured garments share the same
silhouette when flattened to low-res grayscale.

To fix this for production, the highest impact change would be higher-resolution colour images. Colour alone would separate many of these (e.g., fabric texture, print patterns), and more pixels would preserve
structural details like necklines and sleeve cuts that the model currently can't see.
