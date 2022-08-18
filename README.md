# Modules

## Learning Goals

- Explain Angular modules.

## Angular Modules

Although creating a multi-module Angular application is out of scope for this
course, our Angular application we've been building still has a "root" module,
as all Angular applications do, so we will explore the aspects that make up a
module.

A module is a grouping of components and has configuration information
associated with it that is applied to all its children components, and in the
case of multi-module application, its child modules.

Let's look at our current `app.module.ts`:

```typescript
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
import { FormsModule } from "@angular/forms";

import { AppComponent } from "./app.component";
import { HeaderComponentComponent } from "./header-component/header-component.component";
import { ApplicationComponentComponent } from "./application-component/application-component.component";
import { ConversationControlComponentComponent } from "./application-component/conversation-control-component/conversation-control-component.component";
import { ContactListComponentComponent } from "./application-component/contact-list-component/contact-list-component.component";
import { ConversationHistoryComponentComponent } from "./application-component/conversation-history-component/conversation-history-component.component";
import { ConversationThreadComponentComponent } from "./application-component/conversation-history-component/conversation-thread-component/conversation-thread-component.component";
import { SendMessageComponentComponent } from "./application-component/conversation-history-component/send-message-component/send-message-component.component";
import { ContactComponentComponent } from "./application-component/contact-list-component/contact-component/contact-component.component";
import { SenderMessageComponentComponent } from "./application-component/conversation-history-component/conversation-thread-component/sender-message-component/sender-message-component.component";
import { UserMessageComponentComponent } from "./application-component/conversation-history-component/conversation-thread-component/user-message-component/user-message-component.component";

@NgModule({
  declarations: [
    AppComponent,
    HeaderComponentComponent,
    ApplicationComponentComponent,
    ConversationControlComponentComponent,
    ContactListComponentComponent,
    ConversationHistoryComponentComponent,
    ConversationThreadComponentComponent,
    SendMessageComponentComponent,
    ContactComponentComponent,
    SenderMessageComponentComponent,
    UserMessageComponentComponent,
  ],
  imports: [BrowserModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

Looking at this `app.module.ts` file, you will see that several entries have
been added by the Angular CLI as we were adding components in the previous
sections. That's because the module is how Angular learns about the various
aspects of our application, including:

1. `declarations`: this is where we tell Angular about the components our
   application should know about. This is also where we would add custom
   directives and pipes if we had any.
2. `imports`: this is where we tell Angular about other Angular Module we need
   to use in our components in this module. For example, this is where we added
   the `FormsModule` import when we wanted to use `ngModel`.
3. `providers`: this is where we will tell Angular about classes we want to be
   able to use Dependency Injection with - don't worry about not knowing what
   "Dependency Injection" is, we will cover that in our section about services.
4. `bootstrap`: this is where we tell Angular which components to start our
   application with.
