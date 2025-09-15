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
      <th><strong>Rama / Grupo</strong></th>
      <th><strong>Para qué sirve</strong></th>
      <th><strong>Ejemplos</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>main</strong></td>
      <td>Rama principal. Contiene el código en producción, siempre estable.</td>
      <td><code>main</code></td>
    </tr>
    <tr>
      <td><strong>develop</strong></td>
      <td>Rama de integración. Aquí se unen todas las features antes de crear un release.</td>
      <td><code>develop</code></td>
    </tr>
    <tr>
      <td><strong>feature/</strong></td>
      <td>Para crear nuevas funcionalidades del proyecto.</td>
      <td><code>feature/login</code><br><code>feature/menu</code></td>
    </tr>
    <tr>
      <td><strong>release/</strong></td>
      <td>Para preparar versiones listas para producción.</td>
      <td><code>release/release-1.0</code><br><code>release/release-1.1</code></td>
    </tr>
    <tr>
      <td><strong>hotfix/</strong></td>
      <td>Para corregir errores críticos en producción.</td>
      <td><code>hotfix/fix-bug-login</code><br><code>hotfix/fix-migraciones</code></td>
    </tr>
    <tr>
      <td><strong>bugfix/</strong></td>
      <td>Para corregir errores menores en desarrollo.</td>
      <td><code>bugfix/footer-typo</code><br><code>bugfix/api-timeout</code></td>
    </tr>
    <tr>
      <td><strong>support/</strong></td>
      <td>Para mantener versiones antiguas activas mientras se desarrolla una nueva.</td>
      <td><code>support/v1.0</code><br><code>support/v1.1</code></td>
    </tr>
    <tr>
      <td><strong>experiment/</strong></td>
      <td>Para ideas experimentales o prototipos que pueden o no integrarse.</td>
      <td><code>experiment/new-ui</code><br><code>experiment/ai-integration</code></td>
    </tr>
  </tbody>
</table>

