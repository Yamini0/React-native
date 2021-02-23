# What is React Native?

With the ever-increasing popularity of smartphones, developers are looking into solutions for building mobile applications.
React Native is a framework built by Facebook engineers and based on ReactJS. It allows you to write the code just once using the popular JavaScript (TypeScript) language and create a mobile application for both Android and iOS.

# React Vs React Native

## ReactJS

React has as its main focus Web Development.

- React’s virtual DOM is faster than the conventional full refresh model, since the virtual DOM refreshes only parts of the page.
- You can reuse code components in React, saving you a lot of time. (You can in React Native too.)
- As a business: The rendering of your pages completely, from the server to the browser will improve the SEO of your web app.
- It improves the debugging speed making your developer’s life easier.
- You can use hybrid mobile app development, like Cordova or Ionic, to build mobile apps with React, but is more efficiently building mobile apps with React Native from many points.

## React Native

An extension of React, niched on Mobile Development.

- Its main focus is all about Mobile User Interfaces.
- iOS & Android are covered.
- Reusable React Native UI components & modules allow hybrid apps to render natively.
- No need to overhaul your old app. All you have to do is add React Native UI components into your existing app’s code, without having to rewrite.
- Doesn't use HTML to render the app. Provides alternative components that work in a similar way, so it wouldn't be hard to understand them.
- Because your code doesn’t get rendered in an HTML page, this also means you won’t be able to reuse any libraries you previously used with React that renders any kind of HTML, SVG or Canvas.
- React Native is not made from web elements and can’t be styled in the same way. Goodbye CSS Animations!

# Pros of React Native

- It speeds up the app development process:
  The main advantage of React Native is the ability to create applications for two platforms using one code. So while working on a given function/update, we create them immediately for each mobile platform. For a product released on both platforms, this can save you time and money by up to 30%.

  It’s worth mentioning that thanks to the community support and React Native’s extensibility, the list of supported platforms is growing. You just need to install additional libraries.

- Lower Cost of app development:
  The common source code allows you to build the app with one development team familiar with Javascript. This significantly contributes to the reduction of app development cost. Contrary to native development, you can involve a smaller number of people in the project. It’s because there is no need to “duplicate” teams per platform.

- It ensures stable growth of the app:
  One of React Native’s pros is that RN shares its set of components that “know” how to display the app on a given platform. Thanks to this abstraction, React Native allows the developer to focus on developing the application without going into the details of the platform. So given that, the process of building app features is more stable and resistant to discrepancies between platforms than in separate native teams. This allows for better planning of application releases with new features/upgrades.

- It can integrate with the native application:
  React Native has mechanisms that allow it to integrate with an already existing native application. For this reason, you can find both views that are written natively, as well as views written with React Native in a mobile application. This offers many possibilities.

  Developers can write some views with React Native in order to lower their costs (e.g., account management, purchase summary, etc.). And the rest – which the framework can’t handle – remain native.

  If you want to transfer your application to a cross-platform solution, your existing application can be rewritten in small steps. This approach reduces the chance of errors and allows for a faster release of the new application.

# Cons of React Native

Let’s dive into the disadvantages of React Native.

- It’s not a native solution:
  React Native is a cross-platform technology based on JavaScript. To make this possible, the authors of the framework had to create communication mechanisms between the native world and Javascript. For this reason, an application written in React Native might be slower compared to native applications and take up more space than its native counterpart.

  It’s worth noting that the performance problem can only arise in applications with high dynamism, in which there are continuous/large changes on the screen, such as, for example, action games. Facebook engineers have made every effort to ensure that applications written in React Native render at 60 frames per second (in accordance with the applicable standard), providing the user with a native experience.

- It’s harder to build a cross-platform team:
  React Native is a cross-platform technology. The team should also have knowledge of both the world of web technologies (React, JavaScript, and its ecosystem) and native technologies (project configuration, CI, UX guidelines for the platform). It’s much more difficult to build a team able to cope with all the challenges that may arise in the development of a cross-platform application.
