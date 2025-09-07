# My Hugo Book Site

This project is a website built using the Hugo static site generator with the Hugo Book theme. It features a simple structure with two main menu items.

## Project Structure

```
my-hugo-book-site
├── content
│   ├── _index.md          # Homepage content
│   ├── menu1
│   │   └── _index.md      # Content for the first menu item
│   └── menu2
│       └── _index.md      # Content for the second menu item
├── layouts
│   └── list.html          # Layout for listing content
├── config.toml            # Configuration file for the Hugo site
└── README.md              # Documentation for the project
```

## Getting Started

To get started with this project, follow these steps:

1. **Install Hugo**: Make sure you have Hugo installed on your machine. You can download it from [Hugo's official website](https://gohugo.io/getting-started/installation/).

2. **Clone the Repository**: Clone this repository to your local machine using:
   ```
   git clone <repository-url>
   ```

3. **Navigate to the Project Directory**:
   ```
   cd my-hugo-book-site
   ```

4. **Run the Hugo Server**: Start the Hugo server to view your site locally:
   ```
   hugo server
   ```

5. **Open Your Browser**: Go to `http://localhost:1313` to see your website in action.

## Hugo Book Theme

This project uses the Hugo Book theme, which provides a clean and modern layout suitable for documentation and books. You can customize the theme by modifying the `config.toml` file and the content files in the `content` directory.

## Contributing

If you would like to contribute to this project, feel free to submit a pull request or open an issue for discussion.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.