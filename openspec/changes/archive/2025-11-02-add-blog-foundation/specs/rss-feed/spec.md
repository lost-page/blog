## ADDED Requirements

### Requirement: RSS Feed Generation
The system SHALL automatically generate an RSS/Atom feed of all published posts.

#### Scenario: RSS feed available
- **WHEN** the site is built
- **THEN** an RSS feed is generated at `/index.xml` or `/feed.xml`

#### Scenario: Feed includes recent posts
- **WHEN** accessing the RSS feed
- **THEN** the feed contains recent published posts with title, date, link, and content

### Requirement: Feed Metadata
The system SHALL include proper feed metadata including site title, description, and author information.

#### Scenario: Feed metadata present
- **WHEN** parsing the RSS feed
- **THEN** feed includes channel title, description, link, and language

### Requirement: Feed Auto-Discovery
The system SHALL include feed auto-discovery links in HTML pages for RSS reader detection.

#### Scenario: Auto-discovery link in HTML
- **WHEN** viewing any page source
- **THEN** HTML head includes link tag with `rel="alternate"` pointing to RSS feed

### Requirement: Feed Content Format
The system SHALL format feed entries with complete post content or meaningful excerpts.

#### Scenario: Full content in feed
- **WHEN** a post is included in the RSS feed
- **THEN** the feed entry contains the complete post content or a substantial excerpt

#### Scenario: HTML content in feed
- **WHEN** posts contain formatted content
- **THEN** the feed preserves formatting using HTML in CDATA or properly escaped
