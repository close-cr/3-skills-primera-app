# 3 skills para tu primera app con IA

Si vas a sacar tu primera app con inteligencia artificial, estas son las tres skills que te recomiendo tener sí o sí. Una *skill* es una carpeta con instrucciones que Claude Code lee cuando la necesita. Instalas una vez y las usas cuando quieras.

Ninguna la hice yo: son proyectos de código abierto (licencia MIT) de sus autores. Aquí te dejo qué hace cada una y cómo instalarla.

| # | Para qué sirve | Skill | Autor | Cómo la llamas |
|---|---|---|---|---|
| 1 | **Ciberseguridad**: busca fallas en tu proyecto (claves expuestas, dependencias con huecos, errores de login) | [cyber-neo](https://github.com/Hainrixz/cyber-neo) | Hainrixz | `/cyber-neo` |
| 2 | **Código de calidad**: revisa y prueba por ti, para que no tengas que comprobar tú todo lo que escribió la IA | [gstack](https://github.com/garrytan/gstack) | Garry Tan | `/review`, `/qa`, `/cso` |
| 3 | **Interfaz y diseño**: revisa que tu app sea clara, accesible y bonita de usar | [web-design-guidelines](https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines) | Vercel | `/web-design-guidelines` |

## La forma fácil: que Claude las instale

Abre [Claude Code](https://docs.claude.com/en/docs/claude-code/overview) y pega esto:

```
Instala estas 3 skills en ~/.claude/skills y dime cuando terminen:
1. git clone https://github.com/Hainrixz/cyber-neo.git ~/.claude/skills/cyber-neo
2. git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack && cd ~/.claude/skills/gstack && ./setup
3. npx skills add vercel-labs/agent-skills (y elige web-design-guidelines)
Antes de correr cada comando, léeme qué hace y espera mi sí.
```

Reinicia Claude Code al terminar.

## A mano

Primero necesitas [Git](https://git-scm.com/) y [Node.js](https://nodejs.org/). Para gstack, además, [Bun](https://bun.sh/).

**1. Ciberseguridad (cyber-neo)**
```bash
git clone https://github.com/Hainrixz/cyber-neo.git ~/.claude/skills/cyber-neo
```

**2. Código de calidad (gstack)**
```bash
git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack
cd ~/.claude/skills/gstack && ./setup
```

**3. Interfaz y diseño (web-design-guidelines)**
```bash
npx skills add vercel-labs/agent-skills
```
Cuando te pregunte cuáles, elige `web-design-guidelines`.

## Cómo usarlas

Abre Claude Code dentro de la carpeta de tu app y:

- Antes de publicar: `/cyber-neo` revisa tu proyecto y te da un informe con qué arreglar primero.
- Cada vez que Claude termine de programar algo: `/review` y `/qa` (de gstack).
- Cuando la app ya funcione: `/web-design-guidelines` con el archivo o la carpeta de tu interfaz.

## Reglas de oro

- Si tu app usa una API con clave, **nunca** la pongas dentro del código que se publica. Es lo primero que revisa la skill de ciberseguridad.
- Lo que Claude lee se envía al servicio de Claude para poder responderte.
- Estas skills encuentran muchos problemas, pero no reemplazan a una persona que revise lo crítico (pagos, datos de clientes).
- Instala skills solo de autores que conozcas: una skill puede ordenarle a Claude que ejecute comandos.

Hecho por [CLOSE](https://closecr.com) · [@close.costarica](https://www.instagram.com/close.costarica/)
