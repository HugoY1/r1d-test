import { useState } from "react";
import { useAccount, useConnect, useDisconnect } from "wagmi";
import { InjectedConnector } from "wagmi/connectors/injected";

export default function Home() {
  const { address, isConnected } = useAccount();
  const { connect } = useConnect({ connector: new InjectedConnector() });
  const { disconnect } = useDisconnect();
  const [amount, setAmount] = useState("");

  return (
    <main className="flex min-h-screen flex-col items-center justify-center p-6 bg-white text-gray-900">
      <div className="w-full max-w-md bg-gray-100 rounded-2xl shadow-xl p-6 space-y-4">
        <h1 className="text-xl font-semibold text-center">R1D Staking Portal</h1>
        {!isConnected ? (
          <button
            onClick={() => connect()}
            className="w-full py-2 px-4 bg-black text-white rounded-xl hover:opacity-90"
          >
            Connect Wallet
          </button>
        ) : (
          <div className="space-y-4">
            <div className="text-sm text-gray-600 text-center">
              Connected as: {address}
            </div>
            <input
              type="number"
              value={amount}
              onChange={(e) => setAmount(e.target.value)}
              placeholder="Amount of R1D"
              className="w-full px-4 py-2 rounded-xl border"
            />
            <div className="grid grid-cols-2 gap-2">
              <button className="py-2 bg-green-600 text-white rounded-xl hover:opacity-90">
                Stake sR1D
              </button>
              <button className="py-2 bg-blue-600 text-white rounded-xl hover:opacity-90">
                Stake slR1D
              </button>
            </div>
            <button className="w-full py-2 px-4 bg-gray-800 text-white rounded-xl hover:opacity-90">
              Unstake
            </button>
            <button
              onClick={() => disconnect()}
              className="w-full py-2 px-4 bg-gray-300 text-black rounded-xl hover:opacity-80"
            >
              Disconnect
            </button>
          </div>
        )}
      </div>
    </main>
  );
}
