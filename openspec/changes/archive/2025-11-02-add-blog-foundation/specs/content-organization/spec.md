## ADDED Requirements

### Requirement: Tag Taxonomy
The system SHALL support tagging posts with multiple tags for categorization and filtering.

#### Scenario: Assign tags to post
- **WHEN** a post includes a `tags` field in frontmatter with a list of tags
- **THEN** the post is associated with those tags in the site taxonomy

#### Scenario: Tag listing page
- **WHEN** navigating to the tags index page
- **THEN** all tags used across the blog are listed with post counts

### Requirement: Tag-Filtered Post Lists
The system SHALL generate individual pages for each tag showing all posts with that tag.

#### Scenario: View posts by tag
- **WHEN** clicking on a tag link
- **THEN** a page displays all posts tagged with that tag

#### Scenario: Multiple tags on post
- **WHEN** a post has multiple tags
- **THEN** the post appears in the filtered lists for all assigned tags

### Requirement: Category Taxonomy
The system SHALL support organizing posts into categories for broader topic grouping.

#### Scenario: Assign category to post
- **WHEN** a post includes a `categories` field in frontmatter
- **THEN** the post is associated with those categories

#### Scenario: Category listing page
- **WHEN** navigating to the categories index page
- **THEN** all categories are listed with post counts

### Requirement: Chronological Post Ordering
The system SHALL order posts by date with newest posts first by default.

#### Scenario: Posts listed by date
- **WHEN** viewing a list of posts
- **THEN** posts are displayed in reverse chronological order based on date in frontmatter

#### Scenario: Date-based archives
- **WHEN** viewing archive pages
- **THEN** posts are grouped and ordered by publication date
