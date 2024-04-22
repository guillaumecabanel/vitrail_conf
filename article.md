# Douleurs 🤕

- Trop d'hétérogénéité dans les composants de nos applications

- Sensations de réinventer la roue à chaque fois

- Besoin de compétences en UI


![solution](images/solution.png)<!-- .element: height="250" -->

- **Design System** : ensemble de règles et de composants réutilisables

- **Component Library** : implémentation technique du Design System

- **Vitrail** : Gem du Design System sur ViewComponent


## ✨ Avantages ✨

- **Uniformisation**

- **Réutilisation**

- **Facilité d'utilisation**



## Exemple

![demo_capture](images/vitrail-demo.png)<!-- .element: height="400" -->



Header

```erb[2,4-6]
<div class="flex justify-between items-end">
  <%= vt_title { "My app" } %>
  <div>
    <%= vt_link_to(:primary, "#") { "New user" } %>
    <%= vt_link_to(:secondary, "#") { "Settings" } %>
  </div>
</div>
```


KPIs

```erb[3-5,7-9]
<div class="flex space-x-8">

  <%= vt_kpi(title: "Registrations", icon: "user") do %>
    <%= @registration_count %>
  <% end %>

  <%= vt_kpi(title: "Revenue", icon: "circle-euro) do %>
    <%= @revenue %>
  <% end %>

</div>
```


Table

```erb[1,14|3-5|8-12]
<%= vt_table(id: "users") do |table| %>

  <%= table.with_header.with_content("#") %>
  <%= table.with_header.with_content("Name") %>
  <%= table.with_header.with_content("Email") %>

  <% @users.each do |user| %>
    <% table.with_row do |row| %>
      <%= row.with_division.with_content(user.id) %>
      <%= row.with_division.with_content(user.name) %>
      <%= row.with_division.with_content(user.email) %>
    <% end %>
  <% end %>
<% end %>
```
