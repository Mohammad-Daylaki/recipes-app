 - When I enter "egg" as an ingredient (lowercase and singular), Rails should associate "Eggs"

 <!-- here is sign in default code  -->
<h2>Log in</h2>

<%= form_for(resource, as: resource_name, url: session_path(resource_name),:html=>{
  :class =>"form-horizontal"} ) do |f| %>
  <div class="field">
    <%= f.label :email %><br />
    <%= f.email_field :email, autofocus: true %>
  </div>

  <div class="field">
    <%= f.label :password %><br />
    <%= f.password_field :password, autocomplete: "off" %>
  </div>

  <% if devise_mapping.rememberable? -%>
    <div class="field">
      <%= f.check_box :remember_me %>
      <%= f.label :remember_me %>
    </div>
  <% end -%>

  <div class="actions">
    <%= f.submit "Log in" %>
  </div>
<% end %>

<%= render "devise/shared/links" %>


<!-- ///////////////////////////////////////////////////////////////////////

 *********************************************
   Here is the default new registration form 
 *********************************************
 -->
<h2>Sign up</h2>

<%= form_for(resource, as: resource_name, url: registration_path(resource_name)) do |f| %>
  <%= devise_error_messages! %>

  <div class="field">
    <%= f.label :email %><br />
    <%= f.email_field :email, autofocus: true %>
  </div>

  <div class="field">
    <%= f.label :password %>
    <% if @minimum_password_length %>
    <em>(<%= @minimum_password_length %> characters minimum)</em>
    <% end %><br />
    <%= f.password_field :password, autocomplete: "off" %>
  </div>

  <div class="field">
    <%= f.label :password_confirmation %><br />
    <%= f.password_field :password_confirmation, autocomplete: "off" %>
  </div>

  <div class="actions">
    <%= f.submit "Sign up" %>
  </div>
<% end %>

<%= render "devise/shared/links" %>




/*             ///////////////////////////////
                  ADD DESCRIPTION TO RECIPE
              ///////////////////////////////

              <%= f.text_area :description, autofocus: true , placeholder: "Enter Recipe description" , id: 'textinput' ,class: 'form-control input-md'%>