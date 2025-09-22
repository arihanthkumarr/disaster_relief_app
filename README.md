# Disaster Relief Coordination System

A modern web-based emergency response platform that connects disaster victims with volunteers and enables administrators to coordinate relief efforts efficiently.

## Features

### Victim Interface
- Emergency request submission with location data
- Phone number validation and geocoding support
- Multiple emergency categories (Water, Food, Medical, Shelter, Evacuation)
- Real-time status tracking of submitted requests
- Address-to-coordinates conversion for precise location mapping

### Volunteer Dashboard
- Real-time view of pending emergency requests
- Interactive map showing request locations
- Request acceptance and status management
- Progress tracking for ongoing assignments
- Auto-refresh capabilities for live updates

### Admin Control Panel
- Comprehensive overview of all system requests
- Analytics dashboard with completion rates and statistics
- Request filtering by status and emergency type
- Data export functionality (CSV format)
- Visual charts for status distribution and request types

## Technical Architecture

### Frontend
- **Streamlit**: Web framework for rapid deployment
- **Custom CSS/HTML**: Modern glassmorphism design with dark gradient theme
- **Responsive Design**: Mobile-friendly interface with proper contrast ratios
- **Interactive Elements**: Real-time form validation and smooth transitions

### Backend
- **Python**: Core application logic
- **Google Sheets API**: Primary data storage with CSV fallback
- **Geocoding Integration**: Address validation and coordinate conversion
- **Data Validation**: Phone number and coordinate validation systems

### Data Management
- **Google Sheets**: Cloud-based storage for real-time collaboration
- **CSV Fallback**: Local storage option when cloud services unavailable
- **Request Tracking**: Unique ID generation and status management
- **Location Services**: Haversine distance calculations for proximity matching

## Installation

### Prerequisites
- Python 3.7+
- Git
- Google Cloud Platform account (optional, for Sheets integration)

### Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/arihanthkumarr/disaster_relief_app.git
cd disaster_relief_app
```

2. Install required dependencies:
```bash
pip install streamlit pandas google-api-python-client oauth2client gspread
```

3. Configure Google Sheets (optional):
   - Create a Google Cloud Project
   - Enable Google Sheets API
   - Create service account credentials
   - Download `service_account.json` to project root
   - Add `SHEET_KEY` to Streamlit secrets

4. Run the application:
```bash
streamlit run app.py
```

## Configuration

### Environment Variables
- `SERVICE_ACCOUNT_JSON`: Google service account credentials
- `SHEET_KEY`: Google Sheets document ID

### Fallback Mode
The system automatically switches to CSV-based storage when Google Sheets configuration is unavailable, ensuring the application remains functional in all environments.

## Usage

### For Victims
1. Select "Emergency Help" from the navigation
2. Fill out personal information and emergency details
3. Provide location via address or coordinates
4. Submit request and receive confirmation with tracking ID

### For Volunteers
1. Access "Volunteer Portal" to view pending requests
2. Review request details and locations on the map
3. Accept requests by providing contact information
4. Update status to "Complete" when assistance is provided

### For Administrators
1. Use "Command Center" for system oversight
2. Monitor real-time statistics and completion rates
3. Filter and export data for reporting purposes
4. Track volunteer assignments and system performance

## System Requirements

- **Minimum**: 2GB RAM, modern web browser
- **Recommended**: 4GB RAM, Chrome/Firefox/Safari
- **Network**: Internet connection required for Google Sheets integration
- **Mobile**: Responsive design supports tablets and smartphones

## Security Considerations

- Input validation prevents malicious data entry
- No sensitive data stored in client-side code
- Google Sheets access controlled via service account permissions
- Phone numbers validated but not stored in plain text logs

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -m 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## Deployment Options

### Streamlit Cloud
- Connect GitHub repository directly
- Automatic deployment on code changes
- Built-in secrets management for API keys

### Local Deployment
- Suitable for internal organizational use
- Requires local network access for multiple users
- CSV fallback mode recommended for offline scenarios

### Cloud Platforms
- Compatible with Heroku, Railway, and similar platforms
- Requires environment variable configuration
- Recommend using managed database for production use

## License

This project is open source and available under the MIT License.

## Support

For technical issues or feature requests, please create an issue in the GitHub repository.

## Roadmap

- SMS notification integration
- Multi-language support
- Enhanced analytics dashboard
- Mobile application development
- Integration with emergency services APIs