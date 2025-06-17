# 📱 NativeScript Receipt Scanner App

A modern, feature-rich receipt scanning mobile application built with **NativeScript** and **Angular**. Track your expenses effortlessly with AI-powered receipt scanning, spending insights, and beautiful Material Design UI.

## ✨ Features

### 🏠 **Dashboard**
- Quick spending overview with total and monthly amounts
- Recent receipts preview
- Quick action buttons for scanning and insights
- Personalized greeting based on time of day

### 📄 **Receipt Management**
- Complete receipt library with search and filtering
- Category-based organization (Groceries, Restaurants, Gas, etc.)
- Detailed receipt view with itemized breakdown
- Edit and delete functionality

### 📷 **Smart Scanning**
- AI-powered OCR text extraction
- Automatic merchant and amount detection
- Item-level parsing with prices
- Confidence scoring for scan quality
- Image enhancement for better accuracy

### 📊 **Spending Insights**
- Category breakdown with visual charts
- Monthly spending trends
- Top merchants analysis
- Average spending per receipt
- Period-based filtering (Week/Month/Year)

### ⚙️ **Settings & Preferences**
- Dark/Light mode toggle
- Currency selection
- Auto-categorization settings
- Notification preferences
- Data backup and export options

## 🏗️ Architecture

### **Tech Stack**
- **Framework**: NativeScript 8.x with Angular
- **Language**: TypeScript
- **State Management**: Angular Signals + Services
- **Styling**: CSS with Material Design principles
- **Navigation**: Angular Router with lazy loading

### **Project Structure**
```
src/
├── app/
│   ├── app.component.ts          # Main app shell with TabView
│   ├── app.routes.ts             # Routing configuration
│   ├── features/                 # Feature modules (lazy-loaded)
│   │   ├── home/                 # Dashboard & overview
│   │   ├── receipts/             # Receipt management
│   │   ├── scan/                 # Camera & OCR functionality
│   │   ├── insights/             # Analytics & charts
│   │   └── settings/             # User preferences
│   └── shared/                   # Shared components & services
│       ├── components/           # Reusable UI components
│       ├── services/             # Business logic & data
│       └── models/               # TypeScript interfaces
```

### **Key Design Patterns**
- **Lazy Loading**: Each feature is loaded on-demand
- **Repository Pattern**: Data access abstraction
- **Signal-based State**: Reactive programming with Angular Signals
- **Component Composition**: Reusable, testable components
- **Dependency Injection**: Service-based architecture

## 🎨 Design System

### **Color Palette**
- **Primary**: Emerald (#10b981) - Main accent color
- **Background**: Slate (#0f172a) - Dark theme base
- **Surface**: Slate (#1e293b) - Card backgrounds
- **Text**: Slate (#f1f5f9) - Primary text
- **Secondary**: Slate (#94a3b8) - Secondary text

### **Typography**
- **Headings**: Open Sans, 20-32px, semibold
- **Body**: System default, 14-16px
- **Captions**: 12px for metadata

### **Components**
- **Cards**: Rounded corners (12px), subtle shadows
- **Buttons**: Material Design with hover states
- **Icons**: Emoji-based for cross-platform consistency
- **Navigation**: Bottom TabView with FAB overlay

## 🚀 Getting Started

### **Prerequisites**
- Node.js 16+ 
- NativeScript CLI
- Android Studio (for Android development)
- Xcode (for iOS development, macOS only)

### **Installation**

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd nativescript-receipt-scanner
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Setup NativeScript environment** (for StackBlitz)
   ```bash
   setup-nativescript-stackblitz && ns preview
   ```

4. **Run on device/emulator**
   ```bash
   # Android
   ns run android
   
   # iOS (macOS only)
   ns run ios
   ```

### **Development Commands**
```bash
# Start development with hot reload
ns preview

# Build for production
ns build android --release
ns build ios --release

# Clean build
ns clean
```

## 📱 App Navigation

### **Bottom Tab Structure**
```
┌─────────────────────────────────┐
│  Home  │ Receipts │ 📷 │ Insights │ Settings │
└─────────────────────────────────┘
```

- **Home**: Dashboard with overview and quick actions
- **Receipts**: Full receipt library with search/filter
- **Scan (FAB)**: Camera interface for receipt scanning
- **Insights**: Spending analytics and charts
- **Settings**: App preferences and configuration

### **Key User Flows**

1. **Scan Receipt**: Tap FAB → Camera → Review → Save
2. **View Receipt**: Receipts tab → Select receipt → Detail view
3. **Analyze Spending**: Insights tab → Select period → View charts
4. **Manage Settings**: Settings tab → Toggle preferences

## 🔧 Configuration

### **Environment Variables**
```typescript
// No external APIs required - fully offline capable
// All data stored locally using NativeScript storage
```

### **Customization Options**
- **Categories**: Modify `ReceiptCategory` enum in `receipt.model.ts`
- **Colors**: Update color variables in `app.css`
- **OCR Settings**: Configure `ScanOptions` in `camera.service.ts`

## 📊 Data Models

### **Receipt Interface**
```typescript
interface Receipt {
  id: string;
  date: Date;
  merchant: string;
  total: number;
  category: ReceiptCategory;
  imageUrl?: string;
  items: ReceiptItem[];
  tags: string[];
  createdAt: Date;
  updatedAt: Date;
}
```

### **Scan Result Interface**
```typescript
interface ScanResult {
  confidence: number;
  extractedText: string;
  parsedData: Receipt;
  imageData: string;
  processingTime: number;
}
```

## 🧪 Testing

### **Unit Tests**
```bash
# Run unit tests
npm test

# Run with coverage
npm run test:coverage
```

### **E2E Tests**
```bash
# Run end-to-end tests
npm run e2e
```

## 📦 Build & Deployment

### **Android**
```bash
# Debug build
ns build android

# Release build
ns build android --release --key-store-path <path> --key-store-password <password>
```

### **iOS**
```bash
# Debug build
ns build ios

# Release build
ns build ios --release --for-device
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### **Code Style**
- Use TypeScript strict mode
- Follow Angular style guide
- Use meaningful component and variable names
- Add JSDoc comments for public methods

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **NativeScript Team** for the amazing cross-platform framework
- **Angular Team** for the robust frontend framework
- **Material Design** for the beautiful design system
- **Community Contributors** for plugins and inspiration

## 📞 Support

For support and questions:
- 📧 Email: support@receiptscanner.app
- 🐛 Issues: [GitHub Issues](https://github.com/your-repo/issues)
- 📖 Docs: [NativeScript Documentation](https://docs.nativescript.org/)

---

**Built with ❤️ using NativeScript + Angular**