<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/0xme/0xme/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/0xme/0xme/output/github-contribution-grid-snake.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/0xme/0xme/output/github-contribution-grid-snake.svg">
</picture>

## 1) Buscar jogador por **Nickname**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/search-nickname?nickname={nome}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "quantidadeContas": 2,
  "contas": [
    {
      "id": "13454812921",
      "nivel": 2,
      "experiencia": 48,
      "nickname": "7xHub-#727",
      "regiao": "br"
    },
    {
      "id": "13429214319",
      "nivel": 2,
      "experiencia": 48,
      "curtidas": 98,
      "nickname": "7xhub-#828",
      "regiao": "br"
    }
  ]
}
```

**Erros**
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 2) Informações do jogador (por **UID**)
**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/info-player?uid={uid_player}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "data": {
    "Identificacao": {
      "ID": "1033857091",
      "Nickname": "@Totosoㅤ7x'",
      "Nivel": 72,
      "Experiencia": 3427718,
      "Regiao": "br"
      // demais campos de Identificacao
    },
    "Status": {
      "RankAtual": 325,
      "MelhorRank": 325,
      "PontosRank": 5580,
      "RankCS": 319,
      "MelhorRankCS": 319,
      "PontosCS": 82
      // demais campos de Status
    },
    "Personalizacao": {
      "Emblema": 1001000089,
      "QuantidadeEmblemas": 68,
      "Banner": 901000253,
      "Titulo": 905090075,
      "FotoPerfil": 902000121
      // demais campos de Personalizacao
    },
    "Datas": {
      "CriacaoConta": "25/05/2019, 17:25:07",
      "UltimoLogin": "11/10/2025, 16:17:00"
      // demais campos de Datas
    },
    "Social": {
      "Curtidas": 10291,
      "Assinatura": "Se joga no estilo!",
      "Genero": "GENDER_MALE",
      "Idioma": "Language_CN_TRADITIONAL"
      // demais campos de Social
    },
    "Premium": {
      "ElitePass": "Ativo",
      "NivelPrime": 4
      // demais campos de Premium
    },
    "Guilda": {
      "Nome": "Equipeㅤ7x'ㅤ☕",
      "Nivel": 3,
      "Membros": "7/30",
      "Lider": true
      // demais campos de Guilda
    },
    "Pet": {
      "Nome": "ALOK_BR",
      "Nivel": 5,
      "Experiencia": 1792,
      "Skin": 1310000024,
      "Habilidade": 1315000012
      // demais campos de Pet
    },
    "Diamantes": {
      "CustoResgate": 800
    },
    "Habilidades": [
      { "ID": 5806, "Slot": 0 },
      { "ID": 1806, "Slot": 1 },
      { "ID": 6906, "Slot": 2 },
      { "ID": 5206, "Slot": 3 }
      // demais habilidades
    ],
    "Outfits": [
      205048012,
      204000090
      // demais outfits
    ],
    "Imagens": {
      "Avatars": [
        "https://files.catbox.moe/bjy5y2.png",
        "https://files.catbox.moe/5rkaaj.webp"
      ],
      "OutFits": [
        "https://files.catbox.moe/da81ms.jpeg",
        "https://files.catbox.moe/7liguz.webp"
      ]
    }
  }
}
```

**Erros**
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 3) **Lista do desejos**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/lista-desejos?uid={uid_player}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "quantidade": 2,
  "wishlist": [
    {
      "itemId": 909039014,
      "releaseTime": "1738623117"
    },
    {
      "itemId": 909045010,
      "releaseTime": "1738623338"
    }
  ]
}
```
**Erros**:
- 404 `{ "type": "wishlist_not_found" }`
- 400 `{ "type": "invalid_request" }`
- 500 `{ "type": "erro_interno" }`
---

## 4) **Inspecionar AcessToken & WebToken**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/info-token?access_token={acess_token}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "tokens": {
    "web": {
      "player": {
        "id": 1033857091,
        "nickname": "@Totosoㅤ7x'",
        "level": 72,
        "experience": 3427718,
        "region": "BR"
      }
    },
    "game": {
      "token_info": {
        "uid": 11854471726266,
        "open_id": "Xxxx-Xxxx-Xxxx",
        "app_id": 100067,
        "platform": 3,
        "login_type": 0,
        "login_platform": 11,
        "main_active_platform": 11,
        "scope": [
          "get_user_info",
          "get_friends",
          "payment",
          "send_request"
        ],
        "created_at": "06/10/2025, 03:27:52",
        "expires_at": "21/10/2025, 03:27:52"
      }
    }
  }
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 401 `{ "type": "invalid_token" }`
- 500 `{ "type": "erro_interno" }`
---

## 5) **Tabela de classificação (Pontos)**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/tabela-pontos?region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "region": "br",
  "quantidade": 2,
  "leaderboard": [
    {
      "player_id": "10001",
      "nickname": "JogadorX",
      "points": 7610,
      "position": 1
    },
    {
      "player_id": "10002",
      "nickname": "JogadorY",
      "points": 9661,
      "position": 2
    }
  ]
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 400 `{ "type": "region_not_implemented" }`
- 404 `{ "type": "no_players_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 6) **Ranking Passe (Regional)**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/rank-passe?region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "region": "br",
  "quantidade": 2,
  "leaderboard": [
    {
      "nickname": "JogadorX",
      "pass_level": 8193,
      "position": 1,
      "region": "BR"
    },
    {
      "nickname": "JogadorY",
      "pass_level": 7759,
      "position": 2,
      "region": "BR"
    }
  ]
}
```
**Erros**:
- 404 `{ "type": "no_players_found" }`
- 400 `{ "type": "invalid_request" }`
- 500 `{ "type": "erro_interno" }`
---

## 7) **Ranking Passe (Global)**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/rank-passe-global?auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "quantidade": 2,
  "leaderboard": [
    {
      "nickname": "JogadorX",
      "pass_level": 55555,
      "position": 1,
      "region": "BD"
    },
    {
      "nickname": "JogadorY",
      "pass_level": 15542,
      "position": 2,
      "region": "IND"
    }
  ]
}
```
**Erros**:
- 404 `{ "type": "no_players_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 8) **Check ban**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/check-ban?uid={uid_player}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "verification": "completed",
  "account_status": {
    "account_id": "1033857091",
    "identity": "@Totosoㅤ7x'",
    "profile_data": {
      "current_level": 72,
      "total_likes": 10291,
      "server_location": "BR"
    },
    "restrictions": {
      "banned": false,
      "ban_duration_days": 0,
      "account_status": "active"
    }
  },
  "check_result": "account_clean"
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 500 `{ "type": "erro_interno" }`
- 404 `{ "type": "player_not_found" }`

---

## 9) **Versão do jogo/servidor**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/version?auth={auth_key}
```


**Resposta (200)**
```json
{
  "api_provider": "7XHUB APIS",
  "request_status": "successful",
  "game_build": {
    "release": "OB50",
    "client": "1.114.18",
    "server_url": "https://loginbp.ggblueshark.com/"
  },
  "infrastructure": {
    "review_mode": false,
    "online": true,
    "build_version": "1.114.1"
  },
  "last_updated": "2025-10-12T02:20:46.727Z"
}
```
**Erros**:
- 500 `{ "type": "erro_interno" }`
---

## 10) **Carteira do jogador**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/carteira-player?access_token={AcessToken}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "wallet": {
    "player": {
      "nickname": "@Totosoㅤ7x'",
      "region": "br"
    },
    "balance": {
      "current_diamonds": 2,
      "current_gold": 56262,
      "total_diamonds_earned": 15264
    },
    "last_transaction": {
      "last_recharge": "11/10/2025, 03:52:56",
      "last_updated": "11/10/2025, 23:33:02"
    }
  }
}
```

**Erros**:
- 400 `{ "type": "invalid_request" }`
- 401 `{ "type": "invalid_token" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 11) **Carreira do CS**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/carreira-cs?uid={uid_player}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "player": {
    "account_id": "1033857091",
    "server": "br"
    // demais campos de player
  },
  "clash_squad_stats": {
    "current_season": {
      "Games": 7,
      "Wins": 4,
      "Eliminations": 60,
      "HeadshotRate": "75.00%",
      "KdRatio": "2.40"
      // demais campos da temporada atual
    },
    "career": {
      "Games": 1821,
      "Wins": 940,
      "Eliminations": 9740,
      "HeadshotRate": "46.90%",
      "KdRatio": "1.71"
      // demais campos de carreira
    },
    "ranked": {
      "Games": 24,
      "Wins": 15,
      "Eliminations": 145,
      "HeadshotRate": "24.83%",
      "KdRatio": "2.54"
      // demais campos do modo ranqueado
    }
  }
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---
## 12) **Carreira do BR**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/carreira-br?uid={uid_player}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "player": {
    "account_id": "1033857091",
    "server": "br"
    // demais campos de player
  },
  "battle_royale_stats": {
    "career": {
      "solo_stats": {
        "account_id": "1033857091",
        "games_played": "11828",
        "wins": 110,
        "kills": "8266",
        "detailed_stats": {
          "deaths": "11718",
          "top_10": "3904",
          "total_distance_travelled": "15043119",
          "total_survival_time": "5584139",
          "one_game_most_kills": 25,
          "total_damage_taken": "3725392",
          "vehicle_eliminations": 39,
          "total_headshot_kills": "1143"
          // demais campos de detailed_stats (solo)
        }
      },
      "duo_stats": {
        "games_played": "1152",
        "wins": 64,
        "kills": "2179",
        "detailed_stats": {
          "deaths": "1088",
          "top_5": 249,
          "total_distance_travelled": "4574863",
          "total_survival_time": "466237"
          // demais campos de detailed_stats (duo)
        }
      },
      "squad_stats": {
        "games_played": "1277",
        "wins": "144",
        "kills": "3403",
        "detailed_stats": {
          "deaths": "1133",
          "top_3": "375",
          "total_distance_travelled": "5624292",
          "total_survival_time": "715629"
          // demais campos de detailed_stats (squad)
        }
      }
      // demais modos de carreira
    },
    "classic": {
      "solo_stats": { "detailed_stats": {} },
      "duo_stats": { "detailed_stats": {} },
      "squad_stats": { "detailed_stats": {} }
    },
    "ranked": {
      "solo_stats": {
        "games_played": "9",
        "wins": 1,
        "kills": "37",
        "detailed_stats": {
          "deaths": "8",
          "top_10": "4",
          "total_distance_travelled": "36015",
          "total_survival_time": "4826"
          // demais campos de detailed_stats (solo ranqueado)
        }
      },
      "duo_stats": {
        "games_played": "48",
        "wins": 3,
        "kills": "105",
        "detailed_stats": {
          "deaths": "45",
          "top_5": 12,
          "total_distance_travelled": "192199",
          "total_survival_time": "22558"
          // demais campos de detailed_stats (duo ranqueado)
        }
      },
      "squad_stats": {
        "games_played": "83",
        "wins": "5",
        "kills": "266",
        "detailed_stats": {
          "deaths": "78",
          "top_3": "21",
          "total_distance_travelled": "417249",
          "total_survival_time": "55337"
          // demais campos de detailed_stats (squad ranqueado)
        }
      }
    }
  }
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---

## 13) **Likes Diarios (Max 100)**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/likes?uid={uid_player}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "player": {
    "account_id": 1033857091,
    "nickname": "#Regiis7x'ㅤ⁑",
    "level": 72,
    "experience": 3444440,
    "server": "BR"
  },
  "likes": {
    "before": 11210,
    "after": 11310,
    "added": 100,
    "status": 1
  }
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---
## 14) **Informações Básica**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/basic-info?uid={uid_player}&region={region}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "player": {
    "account_id": "1033857091",
    "nickname": "@Totosoㅤ7x'",
    "level": 72,
    "experience": 3428848,
    "likes": 10393,
    "guild": "Equipeㅤ7x'ㅤ☕",
    "server": "BR",
    "version": "OB50",
    "last_login": "13/10/2025, 00:57:56"
  }
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 404 `{ "type": "player_not_found" }`
- 500 `{ "type": "erro_interno" }`
---
## 15) **Converter (WebToken › AcessToken)**

**Exemplo**
```
GET https://7xhub-api.shardweb.app/api/ff/convert-token?webtoken={WebToken}&auth={auth_key}
```

**Resposta (200)**
```json
{
  "developer": "7XHUB APIS",
  "status": "success",
  "account": {
    "id": 1033857091,
    "nickname": "@Totosoㅤ7x'",
    "level": 72,
    "platform": 3,
    "host": "https://client.us.freefiremobile.com"
  },
  "token": "<token>"
}
```
**Erros**:
- 400 `{ "type": "invalid_request" }`
- 400 `{ "type": "token_too_short" }`
- 401 `{ "type": "invalid_token" }`
- 500 `{ "type": "erro_interno" }`
