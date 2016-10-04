# Barcamp2016 website
--
#### Dependencies

- *react*
- *react-dom*
- *webpack*
- *react-redux*
- *redux*
- *babel-loader*
- *babel-core*
- *babel-preset-es2015*
- *babel-preset-react*

### How to run
 `npm install` (First time)

 `webpack-dev-server --progress --colors`

 open `http://localhost:8080` or `http://localhost:8080/webpack-dev-server`

## Get started

### How to add new section

Your code will be written in `/sections/[section_name].jsx` then add the component into `wrapper.jsx`

for example
>***/containers/sections/index.jsx***
>
>~~~~
class Section extends React.Component {
  render() {
    return (
      <div className="section flex flex-center" id="index-section">
        <p className="text">Index</p>
      </div>
    );
  }
}
export default Section;
~~~~

Second, add your component to `wrapper.jsx`
>***/containers/wrapper.jsx***
>
>~~~~
><Section sectionId="section3" />
>~~~~
>I'm passing `sectionId` to my child component. (We are using `id` to link between navbar and `<Section />`)

### How to apply css and naming convention
- Create `[section_name]_static.scss` under `/sass`
- Your new `id` or `className` must start with `[section_name]-`

for example,
>***/containers/sections/register.jsx***
>
>~~~~
><div id="register-wrapper" className="register-top-container"></div>
>~~~~

>***/sass/register_static.scss***
>
>~~~~
>.register-top-container {
>	height: 400px;
>}
>
>#register-wrapper {
>	top: 0px;
>}
>~~~

- Link the `scss` file by add it to `/sass/style.js`

>***/sass/style.js***
>
>~~~~
>...
>import './register_static.scss';
>~~~~
