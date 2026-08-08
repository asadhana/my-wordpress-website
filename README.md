# WordPress Website with Free Templates

This project enables you to build and run a customizable WordPress website locally using **Docker** and **Docker Compose**. It features persistent storage of your themes and plugins, and is designed to work seamlessly across Windows, macOS, and Linux.

---

## Prerequisites

Before running the website, ensure you have the following installed on your machine:
- **Docker**: [Download Docker Desktop](https://www.docker.com/products/docker-desktop/) (comes with Docker Compose)
- **Git** (optional, to clone this repository)

---

## Project Structure

```text
├── docker-compose.yml   # Docker multi-container configuration
├── README.md            # Detailed documentation and usage instructions
└── wp-content/          # Persisted local directory for themes and plugins
    ├── plugins/         # WordPress plugins folder
    └── themes/          # WordPress themes folder
```

The `./wp-content` directory is mapped directly into the WordPress container. Any themes, plugins, or uploads you install will be safely preserved on your local machine.

---

## Step-by-Step Guide to Run Locally

Follow these steps to start the WordPress site on **Windows**, **macOS**, or **Linux**.

### Step 1: Clone or Download the Repository
Clone this repository to your machine:
```bash
git clone <repository-url>
cd my-wordpress-website
```
*(Or download the repository as a ZIP file and extract it).*

### Step 2: Start the Containers
Open your terminal (PowerShell/CMD on Windows, Terminal on macOS/Linux) in the project directory and run:
```bash
docker compose up -d
```
This command downloads the latest official WordPress and MySQL Docker images, creates the network, mounts the local `./wp-content` directory, and starts both services in the background (`-d`).

To check the status of your running containers:
```bash
docker compose ps
```

### Step 3: Complete WordPress Initial Setup
Once the containers are running:
1. Open your web browser and navigate to: **[http://localhost:8080](http://localhost:8080)**
2. You will be greeted by the WordPress Installation Wizard:
   - **Language**: Select your preferred language (e.g., English) and click **Continue**.
   - **Site Information**:
     - **Site Title**: Enter your website's name (e.g., `My Dream Website`).
     - **Username**: Choose an admin username (e.g., `admin`).
     - **Password**: Copy or enter a secure password.
     - **Your Email**: Enter your email address.
   - Click **Install WordPress**.
3. Once the installation is complete, click **Log In** and log in with your credentials.

---

## Installing and Customizing Free Templates

WordPress has a vast repository of thousands of beautiful, high-quality, free templates (themes) you can use. Here is how to find, install, and activate them:

### Recommended Free Themes
Some of the most popular, fast, and highly customizable free themes are:
- **Astra**: Ultra-fast, highly customizable, and perfectly compatible with page builders.
- **OceanWP**: Lightweight, highly extendable, and great for WooCommerce/e-commerce.
- **Neve**: Mobile-first, AMP-compatible, and extremely fast.

### Step-by-Step Theme Installation:
1. In your WordPress Dashboard, go to **Appearance > Themes** on the left-hand menu.
2. Click the **Add New Theme** button at the top.
3. In the search bar on the right, type the name of the theme (e.g., `Astra` or `OceanWP`).
4. Hover over the theme card and click **Install**.
5. Once installed, click **Activate** to apply the theme to your website.

### Importing Ready-Made Starter Templates (Recommended):
To get a fully designed website in minutes without building from scratch:
1. Go to **Plugins > Add New Plugin** in your WordPress Dashboard.
2. Search for **Starter Templates** (by Brainstorm Force, designed for Astra).
3. Click **Install Now** and then **Activate**.
4. Navigate to **Appearance > Starter Templates** or **Plugins > Installed Plugins > Starter Templates > See Library**.
5. Choose your favorite Page Builder (e.g., **Block Editor** or **Elementor**).
6. Browse hundreds of gorgeous free website templates, select one, and click **Import Complete Site**.
7. In a few moments, your website will be fully designed with demo pages, images, and menus!

---

## Useful Docker Commands

Manage your WordPress container environment with these commands:

- **Stop the website**: Stop containers without deleting data:
  ```bash
  docker compose stop
  ```
- **Start the website again**: Start previously stopped containers:
  ```bash
  docker compose start
  ```
- **Shut down containers & remove networks**:
  ```bash
  docker compose down
  ```
- **View container logs**: (useful for troubleshooting)
  ```bash
  docker compose logs -f
  ```
- **Completely reset the database**: Delete containers along with database volume (WARNING: This resets the WordPress site, but preserves files inside `wp-content/`):
  ```bash
  docker compose down -v
  ```

Enjoy building your WordPress website locally!
