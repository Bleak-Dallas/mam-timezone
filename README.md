# 🌍 Timezone Converter with 24h Format Userscript

A **UserScript** that converts UTC timestamps on web pages to your local timezone, displaying the day of the week and using a 24-hour time format. This script is ideal for users who frequently encounter UTC timestamps and want them automatically adjusted to their local time.  
  
## Features  
  
- Converts UTC timestamps to your local timezone.  
- Displays the day of the week (e.g., "Monday").  
- Uses a 24-hour time format by default (configurable to 12-hour format).  
- Handles dynamic content with a **MutationObserver** for real-time updates.  
- Lightweight and easy to configure.  
  
## Installation  
  
1. Install a UserScript manager for your browser:  
   - [Violentmonkey](https://violentmonkey.github.io/) (recommended)  
   - [Tampermonkey](https://www.tampermonkey.net/)  
   - [Greasemonkey](https://www.greasespot.net/)  
  
2. Add the script to your UserScript manager:  
   - Copy the code from [mam-timezone.js](./mam-timezone.js) (or the raw script file).  
   - Create a new script in your UserScript manager and paste the code.  
  
3. Save and enable the script.  
  
## Configuration  
  
To set your local timezone:  
  
1. Open the script in your UserScript manager.  
2. Locate the following line in the code:  
  
   ```javascript  
   const yourTimezoneOffset = -7; // <- CHANGE YOUR TIMEZONE OFFSET
   ```
- Replace `-7` with your UTC offset. For example:
  - `-5` for UTC-5 (Eastern Time during Standard Time).
  - `+1` for UTC+1 (Central European Time).

3. Save the changes.

### Optional: Switch to 12-Hour Time Format

If you prefer a 12-hour time format, locate the following line in the code:

```javascript
hour12: false // Force 24-hour format <- CHANGE IF YOU WANT 12 HOUR TIME
```
Change false to true and save the script.

## How It Works  
  
1. The script identifies UTC timestamps on web pages using a CSS selector.  
2. It converts the timestamps to your local timezone using the IANA timezone standard.  
3. The converted timestamps are displayed in the format:    
   **Weekday, Month Day, Year, HH:MM (24-hour format)**.  
4. A **MutationObserver** ensures that dynamically loaded content is also updated.  
  
## Changelog  
  
### v1.1  
- Added comprehensive code comments for better readability and maintainability.  
  
### v1.0  
- Major updates:  
  - Added weekday display.  
  - Switched to 24-hour time format.  
  - Improved timezone handling using IANA codes.  
  - Removed unnecessary time adjustments.  
  - Added a MutationObserver for dynamic content.  
  
### v0.8  
- Initial release with basic timezone conversion (no seconds).  
  
## Example  
  
### Original UTC Timestamp:  

2025-02-22 14:30

  
### Converted Local Timestamp (UTC-7):  

Saturday, Feb 22, 2025, 07:30

  
## Known Issues  
  
- The script relies on specific CSS selectors to identify timestamps. If the target website changes its structure, the selector may need to be updated.  
- Some websites may use non-standard date formats that the script cannot parse.  
  
## Contributing  
  
Contributions are welcome! If you have suggestions for improvements or encounter issues, feel free to open an issue or submit a pull request.  
  
### To Contribute:  
1. Fork the repository.  
2. Create a new branch for your feature or bug fix.  
3. Commit your changes with clear descriptions.  
4. Submit a pull request.  
  
## License  
  
This project is licensed under the MIT License. See the [LICENSE](https://mit-license.org/) file for details.  
  
## Credits  
  
- **Original Author**: Lemonade (original script)  
- **Modifications**: TurtleTough42 (v1.0 & v1.1)
