# Web Scraping Tool for Food Images

This web scraping tool is designed to help me download food images from Google for training datasets. It is primarily targeted at food-related projects but can be adapted for general-purpose image scraping.

## Features

- Automatically scrapes images from Google Images based on specified search queries.
- Allows setting the maximum number of images to download per query.
- Detects and removes duplicate images to ensure a clean dataset.

## Prerequisites

- **Python 3.6+**: Ensure you have Python installed on your system.
- **Google Chrome**: This tool uses the Chrome browser for web scraping.
- **Selenium WebDriver**: ChromeDriver executable should be compatible with your installed version of Chrome.
- **Required Python Libraries**: Install these using `pip install selenium pillow requests imagehash`.

## Setup

1. **Download ChromeDriver**: Download the ChromeDriver executable for your specific OS from [here](https://sites.google.com/a/chromium.org/chromedriver/downloads). Make sure it matches the version of your installed Google Chrome browser.

2. **Install Dependencies**: Use the following command to install necessary Python libraries:
    ```bash
    pip install selenium pillow requests imagehash
    ```

3. **Update ChromeDriver Path**: Ensure the path to the ChromeDriver executable is correct in the script. Replace the following line with the correct path to your ChromeDriver:
    ```python
    PATH = r'C:/path/to/your/chromedriver.exe'
    ```

## How to Use

### Step 1: Set the Base Directory

- Open the script and locate the following line:
    ```python
    base_directory = f'C:/Users/YourUserName/Desktop/Food AI/images/Malaysian Dish/{current_date}/'
    ```
- Replace `C:/Users/YourUserName/Desktop/Food AI/images/Malaysian Dish/` with the path to the directory where you want the images to be saved. Each search will create a new folder with the current date.

### Step 2: Enter the Food Names to Search

- When you run the script, it will prompt you to enter the names of the food items you wish to search for. Enter these names separated by commas if you have multiple items. For example:
    ```
    Enter the names of the foods you want to search for, separated by commas: Nasi Lemak, Roti Canai, Laksa
    ```
- The script will create separate folders for each food item using the names provided.

### Step 3: Determine the Number of Images to Scrape

- Next, you will be prompted to enter the maximum number of images to scrape for each food item. Enter an integer value:
    ```
    Enter the maximum number of images to scrape for each food item: 50
    ```
- This will limit the number of images downloaded per search query to the specified number.

### Step 4: Scraping Process

- The script will start scraping images from Google based on the search terms provided. It will save each image in the respective food item's folder.

### Handling Duplicates

- After scraping, the tool will check for duplicate images within each folder using perceptual hashing. If duplicates are detected, you will be prompted to decide whether to delete them.

- **Note**: It's recommended to check the similarity percentage before deciding to delete any images. If the similarity is below 50%, the images may be slightly different rather than true duplicates. The script will automatically handle this part by providing you with a prompt.

### Step 5: Deleting Duplicate Images

- Once duplicates are detected, the script will display a message like this:
    ```
    Note: It is preferable to check if the image similarity is below 50% before deciding to delete.
    Do you want to delete all the duplicate images? (y/any key to skip)
    ```
- If you decide to proceed by entering `y`, the script will delete the smaller-sized duplicate images. Otherwise, it will skip deletion.

## Additional Information

- **Image Format**: The images are saved in JPEG format. You can modify the code to support other formats if needed.
- **Logging and Error Handling**: The script prints messages to indicate the progress and any errors encountered during the scraping process, such as network issues or unidentifiable images.

## Troubleshooting

- If you encounter issues with unidentifiable images or the ChromeDriver, ensure that the image URL is accessible and that the ChromeDriver is correctly installed and up to date.
- The script automatically deletes files that cannot be identified as images to maintain data quality.

## Closing the Web Driver

- Once the scraping is complete, the script will close the web driver automatically. Ensure that you allow the script to run to completion to avoid leaving the browser open.

---

By following these steps, you can effectively use this web scraping tool to collect food images from Google for your machine learning or data analysis projects. Feel free to adapt and extend the code for other use cases as needed.
