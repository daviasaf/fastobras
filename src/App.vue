<script setup>
import LocalidadeEmpresa from "./components/LocalidadeEmpresa.vue";
import LocalidadeFuturaEmpresa from "./components/LocalidadeFuturaEmpresa.vue";
import Servicos from "./components/Servicos.vue";
import pessoas1 from "@/assets/pessoas1.jpg";
import pessoas2 from "@/assets/pessoas2.jpg";
import pessoas3 from '@/assets/pessoas3.jpg'
import machine2 from '@/assets/machine2.jpg'


const servicos = [
    {
        titulo: "Desenvolvimento e Projeto",
        url: pessoas1,
        atividades: {
            servico1: "Estudos de Viabilidade: Analisamos e otimizamos a rentabilidade do seu empreendimento.",
            servico2: "Projetos Arquitetônicos e Estruturais: Elaboração rápida e precisa de todas as plantas técnicas.",
            servico3: "Regularização e Licenciamento: Cuidamos de toda a burocracia para iniciar sua obra sem atrasos.",
        },
    },
    {
        titulo: "Execução e Construção",
        url: machine2,
        atividades: {
            servico1:
                "Obras Residenciais e Comerciais: Da fundação aos acabamentos, executados com excelência.",
            servico2:
                "Construção Rápida e Eficiente: Metodologia focada na entrega acelerada, mantendo o padrão de qualidade.",
            servico3:
                "Instalações Completas: Sistemas elétricos, hidráulicos e estruturais seguros e certificados.",
        },
    },
    {
        titulo: "Gerenciamento e Inspeção",
        url: pessoas2,
        atividades: {
            servico1:
                "Controle de Cronograma e Custos: Gestão transparente para evitar atrasos e estouros de orçamento.",
            servico2:
                "Supervisão Técnica Diária: Engenheiros experientes garantindo a conformidade e qualidade em campo.",
            servico3:
                "Vistorias e Laudos: Avaliação técnica de imóveis e perícias para segurança e manutenção.",
        },
    },
    {
        titulo: "Serviços Especiais",
        url: pessoas3,
        atividades: {
            servico1:
                "Reforço e Recuperação Estrutural: Soluções para revitalizar e garantir a segurança de estruturas antigas.",
            servico2:
                "Reformas e Retrofits: Modernização completa de espaços com foco em design e funcionalidade.",
            servico3:
                "Impermeabilização Avançada: Proteção total contra infiltrações em lajes, piscinas e subsolos.",
        },
    },
]
</script>

<template>
  <header class="w-full bg-slate-900 p-4" alt="cabeçalho">
    <h1 class="text-3xl text-center text-gray-50" alt="título do site">FastObras</h1>
  </header>

  <main class="bg-gradient-to-br from-slate-900 to-slate-700">
    <div
      class="w-full bg-gray-700 h-[90vh] flex justify-center items-center flex-col bg-cover bg-center"
      style="background-image: url(../src/assets/machine1.jpg)"
    >
      <p class="text-xl text-white sm:text-2xl md:text-3xl mx-4 text-center">
        A maior construtora do Brasil
      </p>
      <img
        src="../src/assets/pessoa1.jpg"
        class="min-w-40 w-1/5 rounded-full my-5 border-3 border-white"
        alt="homem trabalhando"
      />
    </div>
    
    <div
      class="w-auto bg-gray-100 flex justify-center py-10 flex-wrap"
    >
      <div class="w-1/4 bg-white p-10 rounded mx-10 min-w-50 shadow-lg ">
        <p class="text-center border-b-1 mb-3 text-lg font-semibold text-slate-700">Onde estamos?</p>
        <LocalidadeEmpresa>Macaé</LocalidadeEmpresa>
        <LocalidadeEmpresa>Campos</LocalidadeEmpresa>
        <LocalidadeEmpresa>Rio de Janeiro</LocalidadeEmpresa>
        <LocalidadeEmpresa>São Paulo</LocalidadeEmpresa>
        <LocalidadeEmpresa>Niterói</LocalidadeEmpresa>
      </div>
      <div class="w-1/4 bg-white p-10 rounded mx-10 min-w-50 shadow-lg">
        <p class="text-center border-b-1 mb-3 text-lg font-semibold text-slate-700">Onde estaremos?</p>
        <LocalidadeFuturaEmpresa>Bahia</LocalidadeFuturaEmpresa>
        <LocalidadeFuturaEmpresa>Natal</LocalidadeFuturaEmpresa>
        <LocalidadeFuturaEmpresa>Campinas</LocalidadeFuturaEmpresa>
      </div>
    </div>
    
    <div class="servicos-container">
      <p class="text-center p-10 text-3xl bg-orange-600 text-white w-full">Nossos serviços</p>

      <Servicos v-for="(servico, index) in servicos" :key="index" :url="servico.url">
        <template #nomeservico> {{ servico.titulo }}</template>
        <template #servicos>
          <li v-for="(atividade, chave) in servico.atividades" 
              :key="chave" 
              class=" text-center  border-b border-gray-200 sm:p-5 p-1 ">
            {{ atividade }}
          </li>
        </template>
      </Servicos>
    </div>

    <div class="w-full h-[50vh] flex justify-center items-center bg-gray-100">
      <button class="bg-orange-600 hover:bg-orange-700 text-white font-bold p-5 rounded-xl shadow-lg cursor-pointer transition duration-300">
        Confira nossos produtos
      </button>
    </div>
  </main>
 <footer class="bg-slate-900 text-white py-8">
    <div class="max-w-4xl mx-auto px-4 text-center">
        
        <p class="text-xl font-semibold mb-2 text-orange-600">
            Fale Conosco
        </p>
        <p class="text-gray-300 mb-4">
            (21) 9999-0000 | contato@fastobras.com.br
        </p>

        <p class="text-xs text-gray-500 mt-6 pt-4 border-t border-slate-700">
           @ 2025 FastObras. Todos os direitos reservados.
        </p>
    </div>
  </footer>
</template>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
}
</style>