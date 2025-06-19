# Personal Budget Tracker

A comprehensive, accessible personal finance management application with professional charts and 508 compliance.

## Features

### 📊 Financial Management
- **Income Tracking**: Track multiple income sources (Federal Salary, Navy Retirement, VA Benefits, etc.)
- **Expense Categories**: Organized into Home, Daily Living, Transportation, Entertainment, and Financial sections
- **Real-time Calculations**: Automatic monthly and yearly totals with live updates
- **Summary Dashboard**: Key metrics including total income, expenses, net balance, and savings rate

### 📈 Visual Analytics
- **Interactive Charts**: Monthly income vs expenses, expense breakdown by category, savings trend analysis
- **Professional Tick Marks**: All charts include proper axis labels and grid lines
- **Print-Ready Charts**: Automatically generated charts for professional reports

### ♿ Accessibility & Compliance
- **508 Compliant**: Meets Section 508 accessibility standards
- **WCAG 2.1 Compatible**: Full screen reader support with proper ARIA labels
- **Keyboard Navigation**: Complete keyboard accessibility
- **High Contrast Support**: Supports user preferences for high contrast and reduced motion
- **Skip Links**: Quick navigation for screen reader users

### 💾 Data Management
- **Local Storage**: Automatic data persistence with 30-second auto-save
- **Multi-Year Support**: Track budgets across multiple years
- **Export Options**: CSV and JSON export formats
- **Print Functionality**: One-page summary reports with charts

### 🖨️ Professional Printing
- **Executive Summary**: Clean one-page format with header, summary cards, and charts
- **Chart Integration**: Automatically includes visual analytics in print output
- **Professional Layout**: Optimized for meetings and financial reviews

## File Structure

```
budgetTracker/
├── budget-tracker.html    # Main application file
├── styles.css            # External stylesheet (508 compliant)
├── help.html             # Comprehensive help documentation
└── README.md             # This file
```

## Getting Started

1. **Open the Application**: Open `budget-tracker.html` in any modern web browser
2. **Select Year**: Choose your budget year from the dropdown
3. **Enter Income**: Add your income sources in the Revenue section
4. **Add Expenses**: Fill in expenses across all categories
5. **Review Summary**: Check the summary cards for your financial overview
6. **Save Data**: Click "Save Data" to store your budget locally

## Key Controls

### Top Navigation
- **Save Data**: Store your budget information
- **View Charts**: Interactive chart analysis
- **Print Summary**: Generate professional one-page report
- **Load Data**: Retrieve saved budget information
- **Help & Documentation**: Complete user guide

### Budget Management
- **Add Items**: Use the "+" buttons to add new income sources or expenses
- **Delete Items**: Remove items with the "Delete" button
- **Toggle Sections**: Collapse/expand sections with the "-/+" buttons

## Accessibility Features

- **Screen Reader Support**: Full compatibility with NVDA, JAWS, and VoiceOver
- **Keyboard Navigation**: Tab through all interactive elements
- **Focus Management**: Clear visual focus indicators
- **ARIA Labels**: Descriptive labels for all form controls
- **Live Regions**: Automatic announcements of total updates
- **Progress Bars**: Accessible progress indicators with proper attributes

## Print Features

The application generates professional one-page summaries including:
- Application header with title
- Four summary cards (Income, Expenses, Balance, Savings Rate)
- Three analytical charts with professional formatting
- Optimized for A4 portrait printing

## Browser Support

- Chrome/Chromium (recommended)
- Firefox
- Safari
- Edge
- Mobile browsers (responsive design)

## Technical Details

- **Framework**: Vanilla JavaScript (no dependencies)
- **Styling**: External CSS with 508 compliance
- **Charts**: Native HTML5 Canvas for optimal performance
- **Storage**: Browser localStorage for data persistence
- **Accessibility**: WCAG 2.1 AA compliant

## Version History

- **v2.0.0**: Full 508 compliance, professional charts, help system
- **v1.5.0**: External CSS separation, accessibility improvements
- **v1.4.0**: Interactive chart system with modal display
- **v1.3.0**: Auto-save, export functionality, print layouts
- **v1.2.0**: Dynamic row management, progress bars
- **v1.1.0**: Collapsible sections, multi-year support
- **v1.0.0**: Initial release with core functionality

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please ensure any changes maintain 508 compliance and accessibility standards.

---

**Built with accessibility and usability in mind.**

