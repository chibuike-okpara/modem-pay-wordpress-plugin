# Modem Pay Payment Form

The **Modem Pay Payment Form** plugin allows you to easily integrate secure payment forms into your WordPress site using the Modem Pay payment gateway. Create custom payment pages, collect payments, and redirect users after successful transactions, all with a simple shortcode.

## Features
- Seamless integration with Modem Pay's payment API.
- Customizable payment forms with support for dynamic amounts and custom fields.
- Responsive, modern design that adapts to your WordPress theme.
- Secure form submissions with nonce validation.
- Easy setup with a user-friendly configuration interface.

## Requirements
- WordPress 5.0 or higher.
- PHP 7.4 or higher.
- A Modem Pay account (test or live) to obtain your public API key.

## Installation
Follow these steps to install and activate the Modem Pay Payment Form plugin:

1. **Download the Plugin**:
   - Download the plugin zip file [modempay-payment.zip](https://github.com/murnitur/modem-pay-wordpress-plugin/archive/refs/tags/v1.zip).

2. **Install the Plugin**:
   - Log in to your WordPress admin dashboard.
   - Navigate to **Plugins > Add New**.
   - Click **Upload Plugin** and select the `modempay-payment.zip` file.
   - Click **Install Now**, then **Activate** the plugin.

3. **Verify Installation**:
   - After activation, you should see a new menu item labeled **Modem Pay Forms** in your WordPress admin sidebar.

## Configuration
To set up the plugin, you need to configure your Modem Pay API key and other settings.

1. **Obtain Your Modem Pay Public Key**:
   - Log in to your Modem Pay account (test or live environment).
   - Navigate to the **API Settings** or **Developer** section.
   - Copy your **Public API Key** (use the test key for testing, or the live key for production).

2. **Access Modem Pay Forms Settings**:
   - In your WordPress admin dashboard, go to **Modem Pay Forms > Settings**.
   - Paste your **Public API Key** into the provided field.
   - Save the settings.

3. **Set Necessary Configurations**:
   - Configure additional settings as needed, such as:
     - **Default Currency**: Set to `GMD` or your preferred currency (if supported).
     - **Success Redirect URL**: Specify a default URL for post-payment redirects (optional).
     - **Success Message**: Customize the message shown after a successful payment.
   - Save all changes.

## Creating Your First Payment Form
1. **Navigate to Payment Forms**:
   - Go to **Modem Pay Forms > Add New** in the WordPress admin dashboard.

2. **Configure the Payment Form**:
   - **Title**: Enter a descriptive title for the payment form (e.g., "Event Registration Payment").
   - **Amount**: Set a fixed amount (e.g., `100`) or leave blank to allow users to enter their own amount.
   - **Pay Button Text**: Customize the button text (e.g., "Pay Now").
   - **Redirect URL**: Specify a page to redirect users after payment (optional).
   - **Custom Fields**: Add custom fields (e.g., dropdowns, text inputs) if needed.
   - **Hide Title**: Check to hide the form title on the front end (optional).
   - **Success Message**: Define a custom success message (optional).
   - Click **Publish** to save the payment form.

3. **Note the Payment Page ID**:
   - After publishing, note the **ID** of the payment form (visible in the **Modem Pay Forms** list or URL when editing).

## Adding the Payment Form to a Page
1. **Create or Edit a Page**:
   - Go to **Pages > Add New** or edit an existing page in your WordPress admin dashboard.

2. **Insert the Shortcode**:
   - Add the following shortcode to the page content, replacing `PAGE_ID` with the ID of your payment form:
     ```
     [modem_pay_payment_page id=PAGE_ID]
     ```
     Example: `[modem_pay_payment_page id=1]`

3. **Publish and Test**:
   - Publish or update the page.
   - Visit the page on your site to view the payment form.
   - Test the form using a test payment (if in test mode) to ensure it processes correctly.

## Usage Notes
- **Shortcode**: Use `[modem_pay_payment_page id=PAGE_ID]` to embed payment forms anywhere shortcodes are supported (e.g., pages, posts, widgets).
- **Styling**: The form inherits your theme’s typography and adapts to its layout. Customize colors and styles by editing `assets/modem-pay.css` in the plugin directory.
- **Testing**: Use Modem Pay’s test mode and test API key to simulate payments without real transactions.
- **Security**: The plugin uses nonces to secure form submissions and sanitizes all inputs to prevent vulnerabilities.

## Troubleshooting
- **Form Not Displaying**:
  - Ensure the payment page ID is correct and exists in **Modem Pay Forms**.
  - Verify the public API key is correctly entered in **Settings**.
- **Styling Issues**:
  - Check for theme conflicts by inspecting the form in your browser’s Developer Tools (F12).
  - Adjust `assets/modem-pay.css` to match your theme’s colors or fonts.
- **Payment Errors**:
  - Confirm your Modem Pay API key is valid (test or live).
  - Check the browser Console (F12) for JavaScript errors related to the Modem Pay SDK.
  - Review WordPress debug logs (enable `WP_DEBUG` in `wp-config.php`).
- **Permissions (Local Development)**:
  - If using a local server (e.g., XAMPP), ensure the plugin folder has correct permissions:
    ```bash
    sudo chmod -R 755 /path/to/wordpress/wp-content/plugins/modempay-payment
    ```
- **Plugin Upload Issues**
   - WordPress may need explicit instructions to locate `wp-content` or use direct filesystem access.
     ```bash
     define('FS_METHOD', 'direct');
     define('WP_CONTENT_DIR', '/Applications/XAMPP/htdocs/your-wordpress-folder/wp-content');
     define('WP_CONTENT_URL', 'http://localhost/your-wordpress-folder/wp-content');
     ```
  - Replace `your-wordpress-folder` with your actual folder name.
  - If your site runs on a custom port (e.g., 8080), adjust the URL (e.g., `http://localhost:8080/your-wordpress-folder/wp-content`).  

## Support
For assistance, contact [info@modempay.com](mailto:info@modempay.com) or visit the Modem Pay documentation at [Modem Pay docs](https://docs.modempay.com). If you encounter bugs or have feature requests, please submit them via [issues](https://github.com/murnitur/modem-pay-wordpress-plugin/issues).

## License
This plugin is licensed under the [GPLv2 or later](https://www.gnu.org/licenses/gpl-2.0.html).
