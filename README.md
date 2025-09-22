# CyberFIAP – Segurança Aplicada (Sprint)

Este projeto implementa um pipeline de **CI/CD com foco em segurança**, atendendo aos requisitos da Sprint.  
Foram integradas as ferramentas de análise de código, dependências e aplicação:

## Ferramentas utilizadas
- **SAST (Semgrep)** → análise estática do código-fonte  
- **DAST (OWASP ZAP Baseline)** → análise dinâmica da aplicação em execução  
- **SCA (OWASP Dependency-Check)** → análise de vulnerabilidades em dependências  

## Resultados das análises

### SAST - Semgrep
- Verificação de padrões de segurança no código-fonte.  
- Relatório gerado: `semgrep.sarif` (não foram encontradas vulnerabilidades críticas).  

### DAST - OWASP ZAP Baseline
- Varredura dinâmica contra a aplicação de teste `testphp.vulnweb.com`.  
- Relatórios gerados:  
  - `report_md.md` (Markdown legível)  
  - `report_json.json` (para integrações automáticas)  

**Principais achados:**  
- Falta de cabeçalho de proteção contra Clickjacking  
- Ausência de política CSP (Content-Security-Policy)  
- Falta de tokens Anti-CSRF  

### SCA - Dependency-Check
- Análise das dependências e bibliotecas utilizadas.  
- Relatório gerado em múltiplos formatos (`XML`, `HTML`, `JSON`).  

## Onde encontrar os relatórios
Todos os relatórios estão disponíveis na pasta `dependency-check-report/` e nos arquivos:  
- `report_md.md`  
- `report_json.json`  
- `semgrep.sarif`  

## Conclusão
O pipeline foi configurado com sucesso, executando testes de **SAST, DAST e SCA**.  
Foram identificadas vulnerabilidades de segurança típicas em ambientes de teste, demonstrando a eficácia das ferramentas.  

---
