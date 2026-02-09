/*
README.md
===========
# Site Atacado Farid

Este repositório contém o site institucional do **Atacado Farid**, desenvolvido para divulgação da empresa e de seus principais produtos: gêneros alimentícios, bebidas, materiais de limpeza, higiene, cestas básicas e produtos em geral.

## Objetivo
- Apresentar a empresa
- Divulgar categorias de produtos
- Facilitar contato via WhatsApp
- Fortalecer a presença digital da marca

## Tecnologias
- React
- Tailwind CSS
- Framer Motion
- shadcn/ui

## Como rodar localmente
1. Instale Node.js (LTS)
2. No terminal, execute:
   - npm install
   - npm run dev
3. Acesse: http://localhost:3000

## Deploy (Vercel)
1. Suba o projeto no GitHub
2. Conecte o repositório na Vercel
3. Clique em Deploy

## Contato
Atacado Farid – Araxá/MG
CNPJ: 41.727.249/0001-80

---
Observação: Este site é para uso institucional e comercial.
===========
*/

import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { ShoppingCart, Phone, MapPin } from "lucide-react";

export default function AtacadoFaridSite() {
  return (
    <div className="min-h-screen bg-slate-50">
      {/* Header */}
      <header className="bg-blue-700 text-white">
        <div className="max-w-7xl mx-auto px-6 py-6 flex items-center justify-between">
          <h1 className="text-2xl font-bold">Atacado Farid</h1>
          <a href="https://wa.me/5500000000000" target="_blank" rel="noreferrer">
            <Button className="rounded-2xl shadow">Fale no WhatsApp</Button>
          </a>
        </div>
      </header>

      {/* Hero */}
      <section className="max-w-7xl mx-auto px-6 py-16 grid md:grid-cols-2 gap-8 items-center">
        <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }}>
          <h2 className="text-4xl font-bold mb-4">O melhor preço da cidade. Variedade e muito mais.</h2>
          <p className="text-slate-600 mb-6">
            Soluções completas para o seu abastecimento: gêneros alimentícios, bebidas,
            material de limpeza e higiene, cestas básicas e produtos em geral.
          </p>
          <div className="flex gap-3">
            <Button className="rounded-2xl">Ver Catálogo</Button>
            <Button variant="outline" className="rounded-2xl">Solicitar Orçamento</Button>
          </div>
        </motion.div>
        <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }} className="bg-white rounded-2xl shadow p-6">
          <p className="text-center text-slate-500">Área para banner promocional / logo</p>
        </motion.div>
      </section>

      {/* Produtos */}
      <section className="bg-white py-16">
        <div className="max-w-7xl mx-auto px-6">
          <h3 className="text-2xl font-semibold mb-8">Nossas Categorias</h3>
          <div className="grid sm:grid-cols-2 md:grid-cols-4 gap-6">
            {["Alimentos", "Bebidas", "Limpeza", "Higiene"].map((cat) => (
              <Card key={cat} className="rounded-2xl shadow">
                <CardContent className="p-6">
                  <ShoppingCart className="mb-3" />
                  <h4 className="font-semibold text-lg">{cat}</h4>
                  <p className="text-slate-500 text-sm">Variedade com preços competitivos.</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Contato */}
      <section className="max-w-7xl mx-auto px-6 py-16">
        <h3 className="text-2xl font-semibold mb-6">Contato</h3>
        <div className="grid md:grid-cols-3 gap-6">
          <Card className="rounded-2xl shadow"><CardContent className="p-6 flex gap-3 items-center"><Phone /> <span>(00) 00000-0000</span></CardContent></Card>
          <Card className="rounded-2xl shadow"><CardContent className="p-6 flex gap-3 items-center"><MapPin /> <span>Araxá - MG</span></CardContent></Card>
          <Card className="rounded-2xl shadow"><CardContent className="p-6">CNPJ: 41.727.249/0001-80</CardContent></Card>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900 text-slate-300 py-6">
        <div className="max-w-7xl mx-auto px-6 text-sm flex flex-col md:flex-row justify-between gap-2">
          <span>© {new Date().getFullYear()} Atacado Farid. Todos os direitos reservados.</span>
          <span>Desenvolvido para divulgação institucional.</span>
        </div>
      </footer>
    </div>
  );
}
