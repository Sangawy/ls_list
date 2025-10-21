# 📊 Waredat SQL Server Web App | ئەپلیکەیشنی وێبی واریدات

سیستەمێکی تەواوی بەڕێوەبردنی داتای کۆگاکانە کە بە Node.js و SQL Server دروست کراوە. ڕووکاری کوردی/ئینگلیزی و تایبەتمەندی فیلتەرکردن و ڕاپۆرت دروستکردن هەیە.

## 🌟 تایبەتمەندییەکان | Features

- **🔍 گەڕان و فیلتەرکردن** - Real-time search across all data fields
- **📱 Responsive Design** - Works on desktop, tablet, and mobile
- **🖨️ پرینت کردن** - Landscape printing with customizable columns  
- **📄 PDF Export** - Generate detailed reports
- **🌐 بیلینگوال** - Kurdish/English interface
- **⚡ Fast Performance** - Optimized SQL queries with pagination
- **🔒 Security** - Environment-based configuration

## 🏗️ تەکنەلۆژییەکان | Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** Microsoft SQL Server
- **Frontend:** HTML5, Bootstrap 5, JavaScript
- **PDF Generation:** Puppeteer
- **Styling:** Bootstrap Icons, Custom CSS

## 📋 پێداویستییەکان | Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)
- SQL Server database access
- Modern web browser

## 🚀 دامەزراندن | Installation

### 1. کلۆن کردنی پرۆژەکە | Clone the Repository
```bash
git clone https://github.com/yourusername/waredat-sql-server-web-app.git
cd waredat-sql-server-web-app
```

### 2. دامەزراندنی Dependencies
```bash
npm install
```

### 3. Environment Variables ڕێکخستن
Copy `.env.example` to `.env` and update with your database credentials:

```bash
cp .env.example .env
```

Edit `.env` file:
```env
# Server Configuration
PORT=3001
NODE_ENV=production

# Database Configuration - تکایە بە زانیاری خۆت بگۆڕە
DB_SERVER=your-sql-server-host
DB_DATABASE=LS_Company
DB_USER=your-username
DB_PASSWORD=your-password
```

### 4. ئەپلیکەیشن ئەجووڵاندن | Run the Application

**Development mode:**
```bash
npm run dev
```

**Production mode:**
```bash
npm start
```

Application will be available at: `http://localhost:3001`

## 📊 Database Schema

ئەم پرۆژەیە کار دەکات لەگەڵ دوو خشتەی سەرەکی:

### 📋 Persson Table
- کەسانەکان و زانیاری پەیوەندیکردن
- ناو، مۆبایل، ئیمەیڵ، ناونیشان

### 📦 WAREDAT2023 Table  
- زانیاری کاڵا و واریدات
- تراک نامبر، لۆگۆ، وزن، جۆری شمک

## 🎮 بەکارهێنان | Usage

### 🏠 پەڕەی سەرەکی | Main Dashboard
- `/` - پەڕەی کەسانەکان 
- `/waredat2023` - پەڕەی واریدات

### 🔍 گەڕان | Search Features
- **Real-time search** لە هەموو خانەکاندا
- **Advanced filtering** بە زیاتر لە یەک فیلتەر
- **Pagination** بۆ داتای زۆر

### 📄 ڕاپۆرت | Reports
- **PDF Export** - ڕاپۆرتی تەواو
- **Print View** - پرینتی Landscape
- **Custom Columns** - دیاریکردنی کۆڵۆمەکان

## 🌐 Deployment Options

### 1. Vercel (پێشنیار دەکرێت)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

### 2. Railway
```bash
# Install Railway CLI
npm install -g @railway/cli

# Login and deploy
railway login
railway init
railway up
```

### 3. Heroku
```bash
# Install Heroku CLI
# Create app
heroku create your-app-name

# Set environment variables
heroku config:set DB_SERVER=your-server
heroku config:set DB_USER=your-user
heroku config:set DB_PASSWORD=your-password

# Deploy
git push heroku main
```

## ⚙️ Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `PORT` | Server port | `3001` |
| `NODE_ENV` | Environment | `development` |
| `DB_SERVER` | SQL Server host | Required |
| `DB_DATABASE` | Database name | `LS_Company` |
| `DB_USER` | Database username | Required |
| `DB_PASSWORD` | Database password | Required |
| `DB_ENCRYPT` | Enable encryption | `false` |

## 📁 پێکهاتەی پرۆژە | Project Structure

```
waredat-sql-server-web-app/
├── server.js              # Main server file
├── package.json            # Dependencies & scripts
├── .env.example           # Environment variables template
├── .gitignore             # Git ignore rules
├── README.md              # Project documentation
├── public/                # Static files
│   └── index.html         # Landing page
├── views/                 # HTML templates
│   ├── dashboard.html     # Persons dashboard
│   └── waredat2023.html   # Warehouse dashboard
└── .github/               # GitHub configuration
    └── copilot-instructions.md
```

## 🔧 API Endpoints

### Persons Data
- `GET /api/persons` - Get paginated persons data
- `GET /api/persons/search` - Search persons with filters

### Warehouse Data  
- `GET /api/waredat2023` - Get paginated warehouse data
- `GET /api/waredat2023/search` - Search warehouse with filters
- `GET /api/waredat2023/headersearch` - Header-based search

### Utilities
- `GET /api/test` - Test database connection
- `POST /api/generate-pdf` - Generate PDF reports

## 🐛 گرفتە باوەکان | Troubleshooting

### Database Connection Issues
```bash
# Check database server accessibility
telnet your-db-server 1433

# Test connection with SQL Server Management Studio
```

### Port Issues
```bash
# Check if port is in use
netstat -ano | findstr :3001

# Kill process using port
taskkill /F /PID [process-id]
```

### Memory Issues (Puppeteer)
Add to your hosting platform:
```bash
NODE_OPTIONS="--max-old-space-size=1024"
```

## 🤝 بەشداری کردن | Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -am 'Add feature'`
4. Push to branch: `git push origin feature-name`  
5. Submit pull request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

Developed with ❤️ for warehouse management efficiency

## 📞 پشتگیری | Support

- Create an [Issue](https://github.com/yourusername/waredat-sql-server-web-app/issues)
- Contact: your-email@example.com

---

**زیانیار:** ئەم پرۆژەیە بەستەرێکی ئاسان و کاریگەرە بۆ بەڕێوەبردنی داتای کۆگا بە ڕووکاری کوردی/ئینگلیزی.

**Note:** This project provides an easy and efficient interface for warehouse data management with Kurdish/English bilingual support.

## بەکارھێنان | Usage

### سەرەکی | Main Dashboard
- سەردانی `http://localhost:3000` بکە بۆ چوونە ناو داشبۆرد
- Visit `http://localhost:3000` to access the dashboard

### گەڕان | Search Features
- **گەڕان بە ناو | Search by Name**: FirstName یا LastName
- **گەڕان بە پاسپۆرت | Search by Passport**: PassportNumber
- **گەڕانی گشتی | General Search**: هەر کۆلمنێک

### ڕاپۆرت | Reports
- کلیک لە دوگمەی "PDF ڕاپۆرت" بکە بۆ دروستکردنی ڕاپۆرت
- Click "PDF Report" button to generate and download report

## فایلەکان | Project Structure

```
sql/
├── server.js              # سێرڤەری سەرەکی | Main server file
├── package.json           # پێداویستیەکان | Dependencies
├── public/
│   └── index.html         # لاپەڕەی سەرەتایی | Landing page
├── views/
│   └── dashboard.html     # داشبۆردی سەرەکی | Main dashboard
├── .github/
│   └── copilot-instructions.md
└── README.md
```

## API Endpoints

### داتای گشتی | All Data
```
GET /api/persons
```

### گەڕان | Search
```
GET /api/persons/search?name=john&passport=A123456&column=Email&value=test
```

### ڕاپۆرتی PDF | PDF Report
```
POST /api/generate-pdf
Body: { "data": [...] }
```

## تێکنۆلۆژیاکان | Technologies

- **Backend**: Node.js, Express.js
- **Database**: SQL Server (mssql package)
- **Frontend**: HTML5, Bootstrap 5, JavaScript
- **PDF Generation**: Puppeteer
- **Styling**: Bootstrap Icons, Custom CSS

## چارەسەری کێشە | Troubleshooting

### کێشەی پەیوەندی بە داتابەیس | Database Connection Issues
```bash
# Check if SQL Server is accessible
telnet 3.65.212.18 1433

# Verify credentials and database name
```

### کێشەی دامەزراندن | Installation Issues
```bash
# Clear npm cache
npm cache clean --force

# Reinstall dependencies
rm -rf node_modules package-lock.json
npm install
```

### کێشەی PDF | PDF Generation Issues
```bash
# For Linux/Ubuntu - install Chrome dependencies
sudo apt-get update
sudo apt-get install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2
```

## گەشەپێدان | Development

### دۆکسەکانی لۆگ | View Logs
```bash
# Server logs
npm run dev

# Check console for database connection status
```

### زیادکردنی فیچری نوێ | Adding New Features
1. کۆپی بکە لە `server.js` بۆ API endpoint نوێ
2. نوێکردنەوەی `dashboard.html` بۆ فیچری نوێ
3. تاقیکردنەوە لە browser

## بەڵگەنامە | Documentation

- [Express.js Documentation](https://expressjs.com/)
- [Bootstrap 5 Documentation](https://getbootstrap.com/docs/5.3/)
- [mssql Package Documentation](https://www.npmjs.com/package/mssql)
- [Puppeteer Documentation](https://pptr.dev/)

## Support

بۆ پشتگیری تێکنیکی یا پرسیار، پەیوەندی بکە.  
For technical support or questions, please contact the development team.

---

**وەشان | Version**: 1.0.0  
**زمان | Language**: Kurdish/English  
**چوارچێوە | Framework**: Node.js/Express  