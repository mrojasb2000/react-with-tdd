# Appointments System

A React-based appointment management system built with Test-Driven Development (TDD) principles.

## Overview

This application provides a day view for managing salon/spa appointments, allowing users to view scheduled appointments for a specific day and see detailed information about each appointment including customer details, services, and stylist information.

## Features

- **Daily Appointment View**: Display all appointments scheduled for a specific day
- **Interactive Appointment Selection**: Click on appointment times to view detailed information
- **Customer Information Display**: Show customer name and phone number
- **Service Details**: Display service type, stylist, and appointment notes
- **Responsive Time Display**: Format appointment times in a user-friendly format
- **Empty State Handling**: Show appropriate message when no appointments are scheduled

## Project Structure

```text
appointments/
├── src/
│   ├── AppointmentsDayView.js    # Main components
│   ├── index.js                  # Application entry point
│   └── sampleData.js            # Sample data generation
├── test/
│   └── Appointment.test.js      # Jest test suite
├── package.json                 # Dependencies and scripts
├── webpack.config.js           # Webpack configuration
└── README.md                   # This file
```

## Components

### `Appointment`

A functional React component that displays detailed information about a single appointment.

**Props:**

- `customer` (object): Customer information
  - `firstName` (string): Customer's first name
  - `lastName` (string): Customer's last name  
  - `phoneNumber` (string): Customer's phone number
- `service` (string): Type of service being provided
- `stylist` (string): Name of the stylist
- `notes` (string): Additional appointment notes
- `startsAt` (Date): Appointment start time

**Example Usage:**

```jsx
<Appointment
  customer={{
    firstName: "John",
    lastName: "Doe",
    phoneNumber: "(555) 123-4567"
  }}
  service="Cut & color"
  stylist="Sarah"
  notes="Customer prefers natural colors"
  startsAt={new Date("2023-12-06T10:00:00")}
/>
```

### `AppointmentsDayView`

The main component that displays a list of appointments for a day with interactive selection.

**Props:**

- `appointments` (array): Array of appointment objects

**Features:**

- Displays appointments as a clickable list with time buttons
- Shows detailed view of selected appointment
- Handles empty state when no appointments exist
- Maintains selected appointment state

**Example Usage:**

```jsx
<AppointmentsDayView appointments={sampleAppointments} />
```

### Utility Functions

#### `appointmentTimeOfDay(startsAt)`

Formats a Date object to display time in HH:MM format.

**Parameters:**

- `startsAt` (Date): The appointment start time

**Returns:**

- String: Formatted time (e.g., "10:30")

## Sample Data

The project includes a sample data generator (`sampleData.js`) that creates realistic appointment data using the Faker.js library.

**Generated Data Includes:**

- Customer names and phone numbers
- Random stylist assignments
- Various service types (Cut, Blow-dry, Cut & color, etc.)
- Lorem ipsum notes
- Hourly appointments from 9 AM to 5 PM

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd appointments
```

1. Install dependencies:

```bash
npm install
```

## Development

### Available Scripts

- **Build**: `npm run build` - Creates production build using Webpack
- **Test**: `npm run test` - Runs Jest test suite

### Running the Application

1. Build the project:

```bash
npm run build
```

1. Serve the built files using a local web server or open `dist/index.html` in your browser.

### Running Tests

```bash
npm run test
```

The test suite uses Jest with jsdom environment for DOM testing and includes:

- Component rendering tests
- Customer data display validation
- Interactive appointment selection testing

## Technology Stack

- **React 18.2.0**: UI library for component-based architecture
- **Webpack 5**: Module bundler and build tool
- **Babel**: JavaScript transpiler with React preset
- **Jest**: Testing framework with jsdom environment
- **Faker.js**: Library for generating fake data
- **ES6+ Features**: Modern JavaScript syntax and features

## Development Approach

This project follows Test-Driven Development (TDD) principles:

1. **Red**: Write failing tests first
2. **Green**: Write minimal code to make tests pass
3. **Refactor**: Improve code while keeping tests green

## Browser Compatibility

The application is built with modern JavaScript features and requires:

- ES6+ support
- Modern browsers (Chrome, Firefox, Safari, Edge)

## Contributing

1. Write tests for new features
2. Follow existing code style and formatting
3. Ensure all tests pass before submitting changes
4. Update documentation as needed

## License

ISC License - see package.json for details

## Future Enhancements

Potential improvements could include:

- Add/edit/delete appointment functionality
- Multi-day calendar view
- Appointment scheduling conflicts detection
- Stylist availability management
- Customer history tracking
- Email/SMS reminders
- Responsive mobile design
- Appointment filtering and search
