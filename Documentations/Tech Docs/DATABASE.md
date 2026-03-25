# Database Schema
## Раздельные коллекции с DbRef

### Пример json файла
Collection: campaigns
{
  "_id": "50e99a7c-8b6f-4c1e-9f3a-2d8e7c6b5a4f",
  "name": "Проклятие Страда",
  "description": "Кампания по D&D 5e",
  "isMasterMode": true,
  "createdAt": "2026-03-26T10:00:00Z",
  "settings": {
    "system": "D&D 5e",
    "defaultTags": ["tag1", "tag2", "tag3"]
  }
}

Collection: tags
{
  "_id": "tag1",
  "campaignId": "50e99a7c-8b6f-4c1e-9f3a-2d8e7c6b5a4f",
  "name": "Битва",
  "color": "#FF0000",
  "icon": "⚔️",
  "usageCount": 15
}

Collection: characters
{
  "_id": "char1",
  "campaignId": "50e99a7c-8b6f-4c1e-9f3a-2d8e7c6b5a4f",
  "name": "Арагорн",
  "class": "Следопыт",
  "level": 5,
  "playerName": "Иван",
  "isMasterCharacter": false,
  "stats": {
    "hp": 45,
    "ac": 16,
    "str": 16,
    "dex": 14
  }
}

Collection: sessions
{
  "_id": "sess1",
  "campaignId": "50e99a7c-8b6f-4c1e-9f3a-2d8e7c6b5a4f",
  "date": "2026-03-20T18:00:00Z",
  "duration": 240,
  "description": "Первая сессия",
  "events": [
    {
      "timestamp": "2026-03-20T18:15:00Z",
      "tagId": "tag1",
      "note": "Схватка с гоблинами"
    }
  ],
  "characterUpdates": [
    {
      "characterId": "char1",
      "xpGained": 500,
      "lootReceived": ["Меч +1"]
    }
  ],
  "isCompleted": true
}
### Вот тут надо обсудить