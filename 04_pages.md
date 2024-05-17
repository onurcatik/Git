# How to Create a GitHub Pages Site

## 1. Create a Repository

First, navigate to [GitHub](https://github.com/) and log in to your account. Then, follow these steps:

1. Click on the **+"** icon in the upper-right corner and select **"New repository"**.
2. Name your repository as `username.github.io`, where `username` is your GitHub username (or organization name).
3. Ensure the repository is set to **Public**.
4. Optionally, add a README file, although it's not necessary for the GitHub Pages site.
5. Click on **"Create repository"** to finish.

## 2. Clone the Repository

After creating the repository, you'll need to clone it to your local machine. Open a terminal and run the following command, replacing `username` with your GitHub username:

```bash
git clone https://github.com/username/username.github.io
```

This command will create a local copy of your repository on your machine.

## 3. Add an Index.html File

Navigate into the project folder you just cloned:

```bash
cd username.github.io
```

Now, add an `index.html` file to the project folder. You can use any text editor to create this file and add your HTML content.

## 4. Stage Changes

Once you've added your `index.html` file, you need to stage the changes to be committed. Run one of the following commands:

```bash
git add --all
```

or

```bash
git add .
```

This will stage all the changes in your repository for the next commit.

## 5. Commit Changes

Commit your changes with a descriptive message using the following command:

```bash
git commit -m "Initial commit"
```

Replace `"Initial commit"` with a meaningful message that describes the changes you've made.

## 6. Push Changes

Finally, push your changes to the GitHub repository:

```bash
git push -u origin main
```

This command will push your committed changes to the `main` branch of your GitHub repository.

## 7. View Your Site

Once the push is complete, open a web browser and navigate to `https://username.github.io`, replacing `username` with your GitHub username. You should see your newly created GitHub Pages site live on the web!
