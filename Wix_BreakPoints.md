# Mobile Screen Resolutions & Wix Studio Breakpoints Cheat Sheet

A comprehensive list of the top smartphones with their screen resolutions and recommended breakpoints for Wix Studio web development. This cheat sheet helps you design responsive websites by targeting the most popular devices effectively.

## Recommended Wix Studio Breakpoints

To ensure your website looks optimal across the most popular devices, use the following breakpoints in Wix Studio. These breakpoints are based on common viewport widths of top smartphones.

| **Breakpoint (px)** | **Target Devices**                                            |
|---------------------|---------------------------------------------------------------|
| **320**             | Small phones (e.g., older iPhones like iPhone SE)             |
| **375**             | iPhone 13 Mini, iPhone 14 Mini, Google Pixel 7, Galaxy S23    |
| **420**             | Standard phones (e.g., iPhone 13, iPhone 14, Pixel 7 Pro)     |
| **480**             | Larger phones (e.g., iPhone 15 Plus, Galaxy S23 Ultra)        |
| **1440**            | High-resolution devices (e.g., OnePlus 11, Xiaomi 13 Pro)      |

### Breakpoint Guidelines

- **320px:** Targets very small devices. Ensure content is readable and navigable.
- **375px:** Suitable for most standard smartphones. Optimize layout for typical phone usage.
- **420px:** Accommodates larger smartphones and phablets. Adjust spacing and element sizes accordingly.
- **480px:** Designed for the largest phones and small tablets. Ensure ample space and usability.
- **1440px:** Targets high-resolution displays and larger devices. Perfect for desktops and high-end smartphones.


## Top 15 Smartphones

### iPhones

| **Device**            | **Screen Resolution (px)** | **Width (px)** | **Screen Size (inches)** |
|-----------------------|----------------------------|-----------------|--------------------------|
| iPhone 13 Mini        | 2340 × 1080                | 1080            | 5.4                      |
| iPhone 14 Mini        | 2340 × 1080                | 1080            | 5.4                      |
| iPhone 13             | 2532 × 1170                | 1170            | 6.1                      |
| iPhone 14             | 2532 × 1170                | 1170            | 6.1                      |
| iPhone 15             | 2556 × 1179                | 1179            | 6.1                      |
| iPhone 14 Pro         | 2556 × 1179                | 1179            | 6.1                      |
| iPhone 15 Pro         | 2556 × 1179                | 1179            | 6.1                      |
| iPhone 14 Plus        | 2778 × 1284                | 1284            | 6.7                      |
| iPhone 15 Plus        | 2796 × 1290                | 1290            | 6.7                      |
| iPhone 14 Pro Max     | 2796 × 1290                | 1290            | 6.7                      |
| iPhone 15 Pro Max     | 2796 × 1290                | 1290            | 6.7                      |

### Android Phones

| **Device**              | **Screen Resolution (px)** | **Width (px)** | **Screen Size (inches)** |
|-------------------------|----------------------------|-----------------|--------------------------|
| Google Pixel 7          | 2400 × 1080                | 1080            | 6.3                      |
| Samsung Galaxy S23      | 2340 × 1080                | 1080            | 6.1                      |
| OnePlus 11              | 3216 × 1440                | 1440            | 6.7                      |
| Xiaomi 13 Pro           | 3200 × 1440                | 1440            | 6.73                     |
| Samsung Galaxy S23 Ultra| 3088 × 1440                | 1440            | 6.8                      |
| Google Pixel 7 Pro      | 3120 × 1440                | 1440            | 6.7                      |

*Note: Width (px) refers to the viewport width, which is essential for setting responsive breakpoints.*


## Usage in Wix Studio

When designing your website in Wix Studio, apply these breakpoints to adjust your layout and styling for different devices. Here's how you can structure your responsive design:

1. **Access Breakpoints:**
   - In Wix Studio, navigate to the responsive design settings.
   - Add custom breakpoints matching the pixel widths listed above.

2. **Apply Styles:**
   - For each breakpoint, adjust your elements (text, images, buttons) to ensure they display correctly.
   - Use Wix Studio’s preview feature to test how your site looks on different devices.

3. **Example CSS Media Queries:**
   Although Wix Studio handles most responsive design aspects visually, understanding CSS media queries can be beneficial.

   ```css
   /* Small phones */
   @media (max-width: 320px) {
     /* Styles for very small devices */
   }

   /* Standard phones */
   @media (min-width: 321px) and (max-width: 375px) {
     /* Styles for standard smartphones */
   }

   /* Larger smartphones */
   @media (min-width: 376px) and (max-width: 420px) {
     /* Styles for larger smartphones and phablets */
   }

   /* Extra large phones and small tablets */
   @media (min-width: 421px) and (max-width: 480px) {
     /* Styles for extra large devices */
   }

   /* High-resolution displays and desktops */
   @media (min-width: 1441px) {
     /* Styles for high-resolution and desktop devices */
   }
