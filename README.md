# ASP.NET-special-tags
[Link](https://stackoverflow.com/questions/649428/asp-net-special-tags)


The official name is "server-side scripting delimiters" or "ASP.NET inline expressions". Visual Studio 2008 syntax highlighting settings dialog calls these "HTML Server-Side Script". Microsoft guys call them "code nuggets" in their blogs.

<%@ %> is a Directive for ASP.NET Web Pages. Used for pages and controls to configure page/control compiler settings (<%@ Control Inherits="MyParentControl" %>).

<%@ %> is also an Application Directive. Used to specify application-specific settings for global.asax. Distinct from the page directives as it only uses a different tag set.
<% %> is a Code Render Block (for inline code). One of 4 forms of Embedded Code Blocks. Used for inclusion of server-side code to the Render() method (<% x = x + 1; %>) of the generated class. Format: single/multiline or multiple-linked (e.g. if/then/else interspersed with html) but cannot be used to declare functions.
<%= %> is a Code Render Block (for inline expressions). Used as a shorthand for <%Response.Write(value)%>
<%: %> (unofficially an "Html Encoding Code Block") is the same as previous, but the output is HTML encoded.
<%# %> is a Data-binding Expression. Used for one-way (readonly) or two-way (updateable) binding through Eval, Xpath, Bind, or expressions (e.g. the selected value of a drop-down control). Binds expressions to data-bound control properties through the control's attribute markup, or as a separate tag which generates a DataBoundLiteralControl instance with the value on its Text property. Expressions are evaluated by a DataBinding event handler for the control.
<%#: %> is an HTML Encoded Data-Binding Expression (new in ASP.NET 4.5). It combines the functionality of <%# %> and <%: %>.

<%$ %> is an ASP.NET Expression Builder. Used for runtime expression binding for control properties through the server tag attributes. Used with AppSettings, ConnectionStrings, or Resources (or your own custom extension, for example to use code-behind properties). These assignments are added to the OnInit() method of the generated class.

<%-- --%> is a Server-Side Comment. Used to exclude the contents from compilation (and so will generate errors if a commented-out control is referred to in code-behind). Unlike html comments the contents will not be included in the output.

<!-- #Include ... --> is a Server-Side Include Directive. Used to insert the contents of a file into the page, control or global file. Useful where a user control is overkill, and a master page cannot be used.
