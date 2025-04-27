# Landing Page Maintenance Guide

This guide will help you maintain and customize the FatbikeTas landing page. Whether you're new to web development or need a quick reference, follow these instructions to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the logo and navigation menu. To update:

1. **Logo Text**
```html
<!-- Find this line in the header -->
<a href="#" class="text-2xl font-bold bg-gradient-to-r from-purple-600 to-blue-500 bg-clip-text text-transparent">FatbikeTas</a>
```
- Replace "FatbikeTas" with your desired logo text
- The gradient effect is created by these classes:
  - `bg-gradient-to-r`: Right-direction gradient
  - `from-purple-600 to-blue-500`: Purple to blue color scheme
  - `text-transparent bg-clip-text`: Makes text show gradient

### Hero Section
Located at the top of the page with the main heading and CTA button:

```html
<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-8">
    Fietstas Voor Fatbike
    <span class="block text-2xl sm:text-3xl text-purple-600 mt-4">Tijdelijk 10% Korting</span>
</h1>
```

To modify:
1. Replace "Fietstas Voor Fatbike" with your main heading
2. Update the discount text in the `<span>` element
3. Responsive text sizes are controlled by:
   - `text-4xl`: Base size (mobile)
   - `sm:text-5xl`: Tablet size
   - `lg:text-6xl`: Desktop size

### Features Section
Each feature card follows this structure:

```html
<div class="p-6 bg-white rounded-2xl shadow-xl hover:shadow-2xl transition-shadow duration-300">
    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-6">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Waterdicht Materiaal</h3>
    <p class="text-gray-600">Nog maar enkele waterdichte tassen beschikbaar.</p>
</div>
```

To add new features:
1. Copy the entire `<div>` block
2. Paste within the `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8` container
3. Update the heading and description text
4. Modify the icon SVG as needed

## Fixing Broken Links

### Navigation Menu Links
Current navigation links are:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Voordelen</a>
    <a href="#faq" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">FAQ</a>
    <a href="#contact" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">Contact</a>
</div>
```

To update:
1. Locate the `href` attribute in each `<a>` tag
2. For internal section links, use `#section-id`
3. For external links, use the full URL: `https://example.com`
4. Verify that internal section IDs match their corresponding sections in the HTML

### Call-to-Action (CTA) Buttons
The main CTA buttons currently point to:
```html
<a href="https://amzn.to/4jKQnS4" class="inline-flex items-center px-8 py-4...">
```

To update:
1. Replace `https://amzn.to/4jKQnS4` with your desired URL
2. Test the link after updating
3. Update all instances of this link throughout the page

## Linking Privacy and Terms Pages

### Footer Links Section
Current footer links:
```html
<ul class="space-y-2">
    <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
    <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
</ul>
```

To add privacy and terms pages:
1. Create `privacy.html` and `terms.html` in your root directory
2. Update the links in the footer:
```html
<ul class="space-y-2">
    <li><a href="privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
    <li><a href="terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
</ul>
```

## Troubleshooting

### Common Issues

1. **Broken Internal Links**
   - Check that section IDs match exactly (case-sensitive)
   - Ensure there are no spaces in IDs
   - Example: `href="#features"` must match `id="features"`

2. **Responsive Design Issues**
   - Classes starting with `sm:` apply to screens 640px and up
   - Classes starting with `md:` apply to screens 768px and up
   - Classes starting with `lg:` apply to screens 1024px and up

3. **Missing Styles**
   - Verify Tailwind CSS CDN link is working
   - Check for typos in class names
   - Ensure all required classes are present

### Need Help?
- Check the [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Validate your HTML using [W3C Validator](https://validator.w3.org/)
- Test all links before deploying changes
- Always backup your files before making significant changes

Remember to test your changes across different devices and browsers to ensure consistency in appearance and functionality.