# 🛠️ Flujo de Trabajo - GitFlow

Este proyecto sigue la metodología **GitFlow** para organizar el desarrollo de forma ordenada y colaborativa.

---

## 🌳 Estructura de Ramas y Grupos

### 1️⃣ **main** (rama principal)
- Es el **código en producción**.
- Siempre estable y funcional.
- Solo recibe merges desde `release/` y `hotfix/`.

<table>
  <thead>
    <tr>
      <th>Rama / Grupo</th>
      <th>Para qué sirve</th>
      <th>Ejemplos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>main</strong></td>
      <td>Código en producción, siempre estable</td>
      <td><code>main</code></td>
    </tr>
    <tr>
      <td><strong>develop</strong></td>
      <td>Integración de features antes del release</td>
      <td><code>develop</code></td>
    </tr>
    <tr>
      <td><strong>feature/</strong></td>
      <td>Nuevas funcionalidades</td>
      <td><code>feature/login</code><br><code>feature/menu</code></td>
    </tr>
    <!-- Y así seguís con los demás -->
  </tbody>
</table>
