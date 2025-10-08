# Polkadot Network Interaction  
With this script, you have the capability to connect to the Polkadot network and perform basic operations
const { ApiPromise, WsProvider } = require('@polkadot/api');

// Connect to the Polkadot network
async function connectToPolkadot() {
  // Create an instance of WsProvider with the specified Polkadot network WebSocket URL
  const provider = new WsProvider('wss://rpc.polkadot.io');

  // Create an instance of ApiPromise using the WsProvider
  const api = await ApiPromise.create({ provider });

  return api;
}

// Usage example
(async () => {
  // Connect to the Polkadot network
  const api = await connectToPolkadot();

  // Perform necessary operations with the Polkadot network
  // For example, get block information
  const blockHash = await api.rpc.chain.getBlockHash();
  const blockHeader = await api.rpc.chain.getHeader(blockHash);
  console.log('Latest Block Number:', blockHeader.number.toNumber());
})();
 
# Polkadot Network Interaction  # Polkadot Network Interaction  
