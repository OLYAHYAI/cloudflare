# 🔐 Pentester Portfolio Website

**Omar LYAHYAI - My Journey to Become a Pentester**

A modern, dark-themed cybersecurity portfolio website showcasing homelab projects, technical skills, and security research.

---

## 🎯 Project Overview

This portfolio website was built using a **multi-agent AI collaboration system** with 6 specialized agents:
- **Grok**: Architecture planning and creative design
- **Big-Pickle**: Content analysis and extraction
- **Qwen235**: HTML structure generation
- **Llama70**: CSS framework development
- **GLM**: JavaScript interactivity
- **Gemini**: Documentation and content writing

---

## ✨ Features

### 🎨 Design
- **Dark Cybersecurity Theme**: Black/dark gray backgrounds with neon green accents
- **Responsive Design**: Mobile-first approach, works on all devices
- **Smooth Animations**: Fade-ins, hover effects, and scroll-triggered animations
- **Accessibility**: WCAG compliant with keyboard navigation support

### 🌐 Bilingual Support
- English and French language toggle
- URL structure: `/en/` and `/fr/`
- LocalStorage for language preference

### 📄 Pages & Sections
1. **Home/Hero**: Eye-catching introduction with typing effect
2. **About**: Personal journey and statistics
3. **Projects**: Filterable project showcase (Infrastructure, Security, Docker, Automation)
4. **Skills**: Technical skills organized by category
5. **Blog**: Latest articles and tutorials
6. **Contact**: Contact form and social links

### 🛠️ Technical Features
- Semantic HTML5
- CSS Grid and Flexbox layouts
- Vanilla JavaScript (no dependencies)
- Intersection Observer for scroll animations
- Mobile navigation with hamburger menu
- Back-to-top button
- Project filtering system

---

## 📁 Project Structure

```
WEBSITE_PROJECT/
├── planning/
│   └── architecture.txt          # Grok's architecture plan
├── analysis/
│   └── content_analysis.txt      # Big-Pickle's content analysis
├── html/
│   └── index.html                # Main homepage
├── css/
│   ├── styles.css                # Main stylesheet
│   ├── responsive.css            # Responsive breakpoints
│   └── animations.css            # Animation keyframes
├── js/
│   ├── main.js                   # Core functionality
│   └── animations.js             # Advanced animations
├── assets/
│   ├── images/                   # Project images
│   ├── icons/                    # Icons and favicons
│   └── fonts/                    # Custom fonts
├── docs/
│   └── (documentation files)
└── README.md                     # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Local web server (optional, for testing)

### Installation

1. **Clone or download the project**
   ```bash
   cd /home/f4blox/Desktop/Gemini/opencode/WEBSITE_PROJECT
   ```

2. **Open in browser**
   ```bash
   # Option 1: Direct file access
   open html/index.html
   
   # Option 2: Using Python HTTP server
   python3 -m http.server 8000
   # Then visit: http://localhost:8000/html/
   
   # Option 3: Using Node.js http-server
   npx http-server -p 8000
   ```

3. **For development**
   - Use VS Code with Live Server extension
   - Or any local development server

---

## 🎨 Customization

### Colors
Edit CSS variables in `css/styles.css`:
```css
:root {
    --color-bg-primary: #0a0e27;
    --color-accent-green: #00ff00;
    --color-accent-purple: #b026ff;
    --color-accent-orange: #ff6600;
    /* ... more variables */
}
```

### Content
- **Projects**: Edit project cards in `html/index.html` (search for `.project-card`)
- **Skills**: Modify skill badges in the skills section
- **Blog**: Update blog articles in the blog section
- **Contact**: Change contact information in the contact section

### Images
Place your images in `assets/images/` and update references:
- `proxmox-homelab.jpg`
- `security-lab.jpg`
- `docker-services.jpg`
- `ai-automation.jpg`

---

## 🌍 Deployment

### Cloudflare Pages (Recommended)
1. Create a new repository on GitHub
2. Push the project:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Pentester portfolio"
   git branch -M main
   git remote add origin https://github.com/[username]/cloudflare.git
   git push -u origin main
   ```
3. Connect to Cloudflare Pages:
   - Go to Cloudflare Dashboard > Pages
   - Create new project
   - Connect GitHub repository
   - Build settings:
     - Framework preset: None
     - Build command: (leave empty)
     - Build output directory: `html`
     - Root directory: `/`
4. Add custom domain: `olyhome.site`
5. Your site will be live at: `https://olyhome.site`

### Alternative: GitHub Pages
1. Follow the Cloudflare steps above, but use GitHub repository
2. Go to Settings > Pages
3. Select `main` branch and `/html` folder
4. Your site will be live at: `https://[username].github.io/cloudflare/`

### Netlify
1. Drag and drop the `html/` folder to Netlify
2. Configure build settings if needed
3. Site will be live instantly

### Custom Domain
- Add a `CNAME` file with your domain
- Configure DNS settings with your provider

---

## 📊 Content from GitHub Repository

This portfolio showcases content from: https://github.com/OLYAHYAI/Portfolio

### Featured Projects
1. **Proxmox Homelab Foundation**
   - Virtualization environment setup
   - Network configuration and VM management

2. **Security Lab: Kali Linux & pfSense**
   - Isolated penetration testing environment
   - Security research and testing

3. **Docker Service Orchestration**
   - Containerized services with Docker Compose
   - Efficient homelab management

4. **AI-Powered Workflow Automation**
   - Integration of MCP, Docker, and N8n
   - Intelligent documentation automation

### Technical Skills
- **Infrastructure**: Proxmox VE, Linux, Ubuntu, Networking
- **Security**: Kali Linux, pfSense, SSL/TLS, Penetration Testing
- **Containerization**: Docker, Docker Compose
- **Automation & AI**: N8n, MCP, AI Integration

---

## 🔧 Browser Support

- ✅ Chrome/Edge (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

---

## 📝 To-Do / Future Enhancements

- [ ] Add actual bilingual content (French translations)
- [ ] Implement blog post pages with markdown support
- [ ] Add project detail modal/pages
- [ ] Integrate contact form backend (EmailJS, Formspree)
- [ ] Add dark/light theme toggle
- [ ] Implement search functionality
- [ ] Add analytics (Google Analytics, Plausible)
- [ ] Create CMS integration for easy content updates
- [ ] Add more interactive elements (terminal simulator)
- [ ] Optimize images and add lazy loading

---

## 🤝 Contributing

This is a personal portfolio project, but suggestions are welcome!

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📄 License

© 2025 Omar LYAHYAI. All rights reserved.

---

## 🙏 Acknowledgments

- **Multi-Agent System**: Built with OpenCode AI agent collaboration
- **Design Inspiration**: Cybersecurity and hacker aesthetics
- **Icons**: Font Awesome
- **Fonts**: Google Fonts (Roboto, Fira Code)

---

## 📞 Contact

- **Email**: contact@olyahyai.com
- **GitHub**: [@OLYAHYAI](https://github.com/OLYAHYAI)
- **LinkedIn**: [Omar LYAHYAI](https://linkedin.com/in/olyahyai)

---

**Built with ❤️ and 💻 by Omar LYAHYAI**
