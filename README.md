# US State Data Breach Rules - Interactive Reference

An interactive web application for viewing and comparing data breach notification laws across all 50 US states and the District of Columbia. This tool serves as a comprehensive reference for cybersecurity professionals, legal teams, and compliance officers researching state-specific breach notification requirements.

## Overview

This application provides an elegant, searchable interface to explore:
- **Personal Information (PII) definitions** by state
- **Data breach definitions** and triggers
- **Risk of harm analysis** requirements
- **Notification timelines** for individuals, attorneys general, and credit agencies
- **Notice content and delivery methods**
- **Penalties and exemptions**
- **Statute citations and source links**

## Features

### 🗺️ Interactive State Selection
- Visual grid of all 50 states + DC
- Search/filter states by name or code
- Active state highlighting
- Organized alphabetically

### 📊 Detailed State Information
- Row-based layout showing all breach notification fields
- Statute citations with visual pill badges
- Clickable source URLs to official legal resources
- Clear labeling of each legal requirement

### 🔍 Advanced Filtering
- **Field filter**: Focus on specific requirements (PII definition, timing, penalties, etc.)
- **Text search**: Find specific terms within the active state's data
- Real-time filtering with no page reloads

### 📁 Data Import
- Upload TSV (tab-separated values) files
- Automatically parses and maps data to states
- Supports spreadsheet exports from Google Sheets, Excel, etc.

### 🎨 Modern UI/UX
- Dark theme optimized for extended reading
- Responsive design (desktop, tablet, mobile)
- Smooth animations and transitions
- Accessibility-focused markup

## Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Optional: A text editor for customizing the application

### Installation

1. **Clone or download** this repository to your local machine:
   ```bash
   git clone <repository-url>
   cd Code
   ```

2. **Open the application**:
   - Simply double-click `flag.html` to open in your default browser
   - Or use a local web server:
     ```bash
     python -m http.server 8000
     ```
     Then navigate to `http://localhost:8000/flag.html`

### Loading Your Data

The application includes sample data for a few states (Alabama, California, Texas). To load your complete dataset:

#### Option 1: Upload TSV File
1. Click the "Load rules from TSV" file input at the top of the details panel
2. Select your `.tsv` file (tab-separated values)
3. Data will automatically populate all states

#### Option 2: Modify the HTML
1. Open `flag.html` in a text editor
2. Find the `STATES` array in the `<script>` section
3. Add or modify state objects following the existing pattern

### TSV File Format

Your TSV file should include the following columns (tab-separated):

```
Serial No.	State / Jurisdiction	Statute(s) Citation	Definition of Personal Information (PII)	Definition of Breach	Risk of Harm Analysis	Timing: Notification to Individuals	Timing: Notification to Attorney General (AG)	Timing: Notification to Credit Agencies	Contents of Notice (to Individuals)	Method of Notice (to Individuals)	Penalties for Non-Compliance	Key Exemptions	Source URL	Notes / Other Requirements
```

See `Untitled spreadsheet - Sheet1.tsv` for a complete example with 8 states.

## Usage Guide

### Viewing State Data

1. **Select a state** from the left panel by clicking on its card
2. The details panel on the right will populate with that state's requirements
3. All fields are displayed as rows with labeled sections

### Filtering Information

**By Field Type:**
- Use the "Show all fields" dropdown to focus on specific categories
- Options include: Statute Citation, PII Definition, Breach Definition, Timing requirements, etc.

**By Search Term:**
- Use the search box to find specific words or phrases
- Search applies to both field labels and content
- Works in combination with field filter

### Understanding the Data

Each state's information is organized into standardized fields:

- **Statute(s) Citation**: Legal code references (e.g., "Cal. Civ. Code §§ 1798.29")
- **PII Definition**: What constitutes personal information under state law
- **Breach Definition**: Legal trigger for notification requirements
- **Risk of Harm Analysis**: Whether harm assessment affects notification duty
- **Timing - Individuals**: Deadline for notifying affected persons
- **Timing - AG**: When/if Attorney General notification is required
- **Timing - Credit Agencies**: Requirements for credit bureau notification
- **Notice Content**: What must be included in notifications
- **Notice Method**: Allowed delivery channels (written, electronic, substitute)
- **Penalties**: Consequences for non-compliance
- **Exemptions**: Safe harbors and exceptions
- **Source URL**: Link to official statute or guidance
- **Notes**: Additional requirements or context

## Customization

### Styling
All CSS is embedded in the `<style>` section of `flag.html`. Key variables are defined in `:root`:

```css
:root {
  --bg: #0f172a;              /* Main background */
  --card-bg: #111827;         /* Card backgrounds */
  --accent: #2563eb;          /* Primary accent color */
  --text-main: #f9fafb;       /* Primary text */
  --text-muted: #9ca3af;      /* Secondary text */
  /* ... more variables ... */
}
```

### Adding New Fields
To add a new data field:

1. Update the `FIELD_DEFS` array:
   ```javascript
   { key: "newField", label: "New Field Label" }
   ```

2. Add the field to your TSV column headers

3. Update the `applySheetTsvText()` function to map the new column

## Technical Details

### Technology Stack
- **HTML5** for structure
- **CSS3** with CSS Grid and Flexbox for layout
- **Vanilla JavaScript** (no frameworks required)
- Client-side only - no server needed

### Browser Compatibility
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### File Structure
```
Code/
├── flag.html                          # Main application file
├── Untitled spreadsheet - Sheet1.tsv  # Sample data (8 states)
└── README.md                          # This file
```

## Data Sources

The included sample data is for demonstration purposes. For production use:
- Verify all statutes with official state legal codes
- Consult with legal counsel for compliance interpretation
- Keep data updated as laws change (states frequently amend breach notification laws)

Recommended official sources:
- State legislature websites
- State Attorney General consumer protection pages
- National Conference of State Legislatures (NCSL)
- IT Governance USA breach notification laws database

## Contributing

To add or update state data:

1. Research the state's current breach notification statute
2. Fill in all applicable fields in your spreadsheet
3. Export as TSV and test in the application
4. Verify all citations and links

## License

This project is provided as-is for educational and research purposes.

## Acknowledgments

- Designed for TAMU cybersecurity research project
- Built with accessibility and usability in mind
- Inspired by the need for a unified breach notification reference

## Support

For questions or issues:
- Check existing state data for examples
- Verify TSV file formatting (tabs, not commas)
- Ensure browser JavaScript is enabled

## Version History

- **v1.0** - Initial release with interactive state viewer and TSV import
- Sample data for 8 states included (Tennessee, Ohio, West Virginia, Virginia, Maryland, Delaware, New Jersey, Pennsylvania)

---

**Note**: This tool provides a starting point for breach notification research. Always verify current law with official sources and consult legal counsel for compliance decisions.
