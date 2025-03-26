import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

export default function StartScreen({ onStart }) {
  const [input, setInput] = useState("");

  const handleStart = () => {
    if (input.trim().toLowerCase() === "mulai") {
      onStart();
    }
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen space-y-4">
      <h1 className="text-2xl font-bold">Selamat Datang di Psikotest Ganjil Genap</h1>
      <p>Ketik <strong>"MULAI"</strong> untuk memulai</p>
      <Input
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="Ketik MULAI di sini..."
      />
      <Button onClick={handleStart} disabled={!input.trim()}>
        Mulai
      </Button>
    </div>
  );
}
