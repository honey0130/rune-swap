# Rune Swap

**Rune Swap** is a decentralized application that allows users to manage and trade digital "runes" efficiently using blockchain-based UTXOs. The platform processes user transactions by leveraging an **UTXO pool** for tracking available runes and facilitates multi-tasking for real-time trade processing.

## Features

- **UTXO Pool Management**: Maintain a pool of unspent transaction outputs (UTXOs) that users can utilize for trading.
- **Multi-task Processing**: Handle multiple concurrent tasks (e.g., UTXO checks and processing) to ensure efficient operation and real-time processing.
- **User-Friendly**: Simple interface for interacting with the Rune Swap system and performing transactions.
- **Blockchain Integration**: Potential to integrate with a blockchain for secure and verifiable rune transactions.

## Demo

[Link to live demo or screenshots]

Example:
- **Link**: [Live Demo](http://example.com)
- **Screenshots**:  
  ![Screenshot 1](path/to/screenshot1.png)  
  ![Screenshot 2](path/to/screenshot2.png)

## Installation

To install and run the Rune Swap project locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/rune-swap.git
    cd rune-swap
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Set up environment variables**:
    - Create a `.env` file and configure necessary settings (e.g., API keys or blockchain credentials).

4. **Run the application**:
    ```bash
    npm start
    ```

5. **Access the app**:
    Open your browser and navigate to `http://localhost:3000` (or the relevant URL).

## UTXO Pool Management

The **UTXO Pool** tracks unspent transaction outputs that users can interact with. Here's how the pool and UTXO operations are handled.

### 1. Create the UTXO Pool

The pool is created as a simple in-memory store for UTXOs. Below is an example implementation in JavaScript:

```javascript
class UTXOPool {
  constructor() {
    this.pool = [];
  }

  // Add a new UTXO to the pool
  addUTXO(utxo) {
    this.pool.push(utxo);
  }

  // Check if UTXO exists in the pool by UTXO ID
  checkUTXO(utxoId) {
    return this.pool.find(utxo => utxo.utxo_id === utxoId);
  }

  // Get all UTXOs from the pool
  getAllUTXOs() {
    return this.pool;
  }
}

// Example usage
const utxoPool = new UTXOPool();
utxoPool.addUTXO({
  utxo_id: "1234567890abcdef",
  amount: 50,
  owner: "user1",
  timestamp: "2024-11-27T00:00:00Z"
});
console.log(utxoPool.checkUTXO("1234567890abcdef"));
