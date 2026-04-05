# Bitpoort MCP Server

On-chain blockchain data for AI agents. Connect to real-time and historical data across Ethereum, Bitcoin, and Hyperliquid through 41 structured JSON tools.

## Quick Start

### Claude Desktop / Cursor / Windsurf

Add to your MCP config:

```json
{
  "mcpServers": {
    "bitpoort": {
      "url": "https://bitpoort.com/mcp/sse",
      "headers": {
        "X-API-Key": "YOUR_API_KEY"
      }
    }
  }
}
```

### Get an API Key

Register at [bitpoort.com/register](https://bitpoort.com/register) for a free API key with $10 starting credit.

## Tools (41)

### Whale & Entity Tracking
| Tool | Description |
|------|-------------|
| `get_whale_activity` | Recent whale transactions with labels, tiers, and USD values |
| `get_entity_activity` | Activity history for named entities (Binance, Wintermute, etc.) or addresses |
| `get_exchange_flows` | Exchange inflow/outflow with per-exchange and per-token breakdown |
| `get_token_flows` | Tokens ranked by net buying/selling pressure from DEX swaps |
| `get_wallet_profile` | Complete wallet profile: label, risk score, top tokens, counterparties |

### Intelligence & Signals
| Tool | Description |
|------|-------------|
| `get_intent_detections` | Behavioral patterns (accumulation, distribution, arbitrage, rug signals) |
| `get_trade_signals` | Composite trade signals with direction, score, thesis, and evidence |
| `get_conviction_signals` | 11-source cross-signal correlation with conviction score (0-100) |
| `get_predictions` | ML price predictions (LightGBM + LSTM, 19 tokens, 5m/10m/15m) |
| `get_smart_wallets` | Top wallets by 7-day trading performance |
| `get_mev_leaderboard` | MEV bot rankings by extracted value |
| `get_intelligence_feed` | Unified event feed from 6 sources (whales, intents, liquidations, MEV, signals) |

### Token Discovery
| Tool | Description |
|------|-------------|
| `get_emerging_tokens` | Emerging tokens ranked by momentum, smart money interest, holder growth |
| `get_trending_tokens` | Tokens ranked by swap volume with buy/sell ratio |

### Search & Q&A
| Tool | Description |
|------|-------------|
| `search_rag` | Semantic search over 2.1M+ indexed blockchain events (hybrid dense + BM25) |
| `ask_blockchain` | Natural language questions about blockchain activity |
| `get_network_summary` | Structured network overview: hourly stats, whale activity, system health |

### Blockchain Data
| Tool | Description |
|------|-------------|
| `query_blocks` | Recent blocks with tx count and gas used |
| `query_transactions` | Transactions with USD values, types, and method names |
| `inspect_block` | Full block detail including transactions, whales, and RAG chunks |
| `get_price_history` | OHLCV price candles, 1-minute resolution, 20 tokens |

### Risk & Alerts
| Tool | Description |
|------|-------------|
| `get_risk_briefing` | Security-focused briefing: anomalies, intents, risk scores |
| `get_alarm_feed` | Triggered on-chain events with severity and USD values |
| `get_alarm_categories` | Available alarm categories with thresholds |

### Cross-Chain
| Tool | Description |
|------|-------------|
| `get_cross_chain_signals` | ETH on-chain to Hyperliquid perpetual correlation signals |
| `get_btc_flows` | Bitcoin whale flows with 2.3M labeled addresses (CIOH clustering) |

### Hyperliquid
| Tool | Description |
|------|-------------|
| `get_hl_market` | Smart money positioning, funding rates, open interest |
| `get_hl_traders` | Top perp traders by smart money score, win rate, Sharpe ratio |

### Direct Ethereum RPC
| Tool | Description |
|------|-------------|
| `rpc_get_balance` | ETH balance with entity label |
| `rpc_get_block` | Block details with optional transaction list |
| `rpc_get_transaction` | Full transaction details with entity labels and receipt |
| `rpc_get_logs` | Contract event logs (transfers, swaps, approvals) |
| `rpc_get_contract_info` | Contract detection, code size, entity classification |
| `rpc_read_contract` | Read contract state (ERC-20 functions, no ABI needed) |
| `rpc_trace_transaction` | Internal call trace with entity labels |

### System
| Tool | Description |
|------|-------------|
| `get_pipeline_status` | 7-stage data pipeline state |
| `get_chain_status` | Per-chain processing status and lag |
| `get_health` | System health score (0-100) |
| `get_stats` | Aggregate statistics across all chains |
| `get_logs` | System logs (sanitized) |
| `get_alerts` | Alert history with severity and resolution |

## Data Coverage

- **Ethereum** -- Full pipeline, Erigon archive node, 500M+ transactions
- **Bitcoin** -- 359K+ entity flows, 2.3M labeled addresses, CIOH clustering
- **Hyperliquid** -- Positions, funding, liquidations, open interest, top traders

## Pricing

| Tier | Price | Rate Limit |
|------|-------|------------|
| Free | $0/mo | 60 req/min |
| Subscription | $99/mo | 300 req/min |
| Enterprise | $499/mo | No limit |

All tiers include $10 free credit. MCP tool calls cost $0.005 each.

## Links

- [Website](https://bitpoort.com)
- [Documentation](https://bitpoort.com/docs)
- [Register](https://bitpoort.com/register)
- [Whale Tracker](https://bitpoort.com/whales)
- [OpenAPI Spec](https://bitpoort.com/openapi.json)

## License

MIT
