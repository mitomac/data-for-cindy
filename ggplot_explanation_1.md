## Code Explanation

### Setting Plot Dimensions
- `options(repr.plot.width=8, repr.plot.height=6)`
  - This line sets the dimensions of plots to be displayed in a Jupyter Notebook. The width is set to 8 inches and the height to 6 inches.

### Creating a Plot with `ggplot`
- `ggplot(weeks_tidy.df, aes(x = Week, y = Value, color = Individual))`
  - This initializes a `ggplot` object. The data from `weeks_tidy.df` is used for the plot. The `aes` function specifies the aesthetics of the plot; `Week` is mapped to the x-axis, `Value` to the y-axis, and different colors are used for each `Individual`.
- `geom_line(linewidth = 1)`
  - Adds line graphs to the plot with a line width of 1. Lines represent data points for each individual over weeks.
- `geom_point(size = 4)`
  - Adds points to the plot, with a size of 4. These points highlight individual data values on the line graphs.
- `labs(title = "Individuals by Week")`
  - Sets the title of the plot to "Individuals by Week".
- `xlab("Week")`
  - Labels the x-axis as "Week".
- `ylab("EtOH (g/Kg)")`
  - Labels the y-axis as "EtOH (g/Kg)", indicating that the values might represent ethanol consumption in grams per kilogram.
- `theme_prism(base_size = 18)`
  - Applies the `prism` theme to the plot with a base font size of 18. This affects the overall appearance of the plot (fonts, colors, etc.).
- `ylim(0,8)`
  - Sets the limits of the y-axis from 0 to 8.

### Saving the Plot
- `ggsave("Individuals_by_week.svg")`
  - Saves the plot as an SVG file. SVG format is vector-based and is useful for high-quality scalable graphics.
- `ggsave("individuals_by_week.pdf")`
  - Saves the plot as a PDF file, which is widely used for distributing documents in a fixed format.
- `ggsave("individuals_by_week.png")`
  - Saves the plot as a PNG file, a commonly used image format that supports lossless data compression.
