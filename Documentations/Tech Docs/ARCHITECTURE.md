### **1.2 ARCHITECTURE.md**
# Архитектура приложения
## Technology Stack
- **Frontend:** .NET MAUI
- **Backend:** Local LiteDB
- **Architecture:** MVVM (CommunityToolkit.MVVM)
- **Data Format:** JSON для экспорта/импорта

## Architecture Diagram
[Views] <--> [ViewModels] <--> [Document Repositories] <--> [LiteDB]
                                    |
                                    V
                           Collections (документы JSON)
                           Вложенные объекты
                           Denormalization

## Структура проекта

NriLogger/
├── NriLogger.Core/              # Бизнес-логика
│   ├── Models/                  # Data models (Campaign, Session, Character)
│   ├── Services/                # Business services
│   │   ├── IDatabaseService.cs  # Интерфейс для LiteDB
│   │   ├── LiteDbService.cs     # Реализация LiteDB
│   │   ├── ExportImportService.cs
│   │   └── SessionLoggerService.cs
│   └── Interfaces/              # Contracts
│
├── NriLogger.UI/                # MAUI приложение
│   ├── Views/                   # XAML страницы
│   │   ├── MainPage.xaml
│   │   ├── CampaignView.xaml
│   │   └── SessionLoggerView.xaml
│   ├── ViewModels/              # MVVM ViewModels
│   │   ├── MainViewModel.cs
│   │   ├── CampaignViewModel.cs
│   │   └── SessionLoggerViewModel.cs
│   ├── Controls/                # Custom controls
│   └── Resources/               # Styles, images
│
├── NriLogger.Tests/             # Unit тесты
│   ├── Services/
│   └── ViewModels/
│
└── README.md

### Архитектуру можно менять, чтобы всем было удобно