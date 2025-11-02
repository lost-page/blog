## Why
The blog's social profile icons (LinkedIn and future X/Twitter) are configured in `hugo.toml` but not visible on the site because the home page isn't using a layout that renders them. Visitors cannot connect with the blog author on social media platforms, reducing engagement and discoverability.

## What Changes
- Enable Home Info Mode in Hugo configuration to display a welcome section on the home page
- Configure the home info section to show social profile icons (LinkedIn currently, X/Twitter ready when available)
- Social icons will appear above blog post listings on the home page

## Impact
- **Affected specs**: Creates 1 new capability
  - `social-profile-links` - Display author social media profile links on home page
- **Affected code**: Modifies Hugo configuration
  - `hugo.toml` - Add `[params.homeInfoParams]` section to enable home info mode
- **User experience**: Social icons will now be visible and clickable on the home page
