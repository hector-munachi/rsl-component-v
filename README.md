# rsl-component-v

A reusable Vue 3 component that simplifies the process of adding Region, State, and LGA selection drop-downs to forms in web applications. This helps developers by eliminating the need to build these inputs from scratch. 

If you're looking for a React version of this reusable Vue 3 component, check [here](https://www.npmjs.com/package/rsl-component).

🔗 **[Demo](https://rsl-component-v.netlify.app/)**

## Installation

Install this package with npm or yarn:

```bash
# If you use npm:
npm install rsl-component-v

# Or if you use Yarn:
yarn add rsl-component-v
```
    
## Usage

Import and use the `InputRSLv` component in your Vue component.
```javascript
<template>
  <InputRSLV />
</template>

<script>
import InputRSLV from 'rsl-component-v';

export default {
  components: {
    InputRSLV,
  },
};
</script>

```

## Example


Here's an example of how you can use the `InputRSLV` component in a form:

```javascript
<template>
  <form>
    <InputSRLV v-model:selected-state="selectedState" v-model:selected-lga="selectedLga" />

    <!-- ... other form fields ... -->

    <button @click.prevent="submitForm">Submit</button>
  </form>
</template>

<script>
import { ref } from 'vue';
import InputRSLV from 'rsl-component-v';

export default {
  components: { InputSRLV },
  setup() {
    const selectedState = ref('');
    const selectedLga = ref('');

    const submitForm = () => {
      // Do something with the captured values, such as sending them to a server
      console.log(selectedState.value, selectedLga.value, InputSRLV.region.value);
    };

    return { selectedState, selectedLga, submitForm };
  }
};
</script>

```
In this example, we passed the `selectedState` and `selectedLga` variables to the `InputSRLV` component using `v-model`. These variables will be updated when the user selects a state and an LGA.

To capture the value of the region input, we accessed the region computed property of the `InputSRLV` component using `InputSRLV.region.value`.

Finally, we defined a `submitForm` function that logs the captured values to the console. You can replace this function with your own logic for handling the form submission.

## `showRegion` prop
The `showRegion` prop is a boolean that controls the visibility of the "Region" input field in the `InputRSLV` component. If set to `true`, the "Region" input field will be displayed, and if set to `false`, the "Region" input field will be hidden.

**To use the** component with the showRegion prop, you can pass it as a prop when you instantiate the component, like this:
```javascript
<template>
  <div>
    <InputRSLV :showRegion="true" />
    <InputRSLV :showRegion="false" />
  </div>
</template>

<script>
import MyComponent from '@/components/MyComponent.vue';

export default {
  components: {
    InputRSLV
  }
};
</script>

```
Here, we are rendering two instances of the `InputRSLV` component, one with `showRegion` set to `true`, and the other with `showRegion` set to `false`. This will render the component twice, once with the Region field, and once without it.

**By default value**, the `showRegion` prop is set to `true`, which means that the "Region" input field will be displayed in the `InputRSLV` component if the prop is not explicitly set to `false`.

**Take note that** if you set `showRegion` to `false`, the first input field will be hidden, and the remaining two input fields will shift up to take its place. If you set `showRegion` to `true`, the "Region" input field will be displayed, and the remaining two input fields will shift down to make space for it.

## Contributing

We welcome and appreciate contributions from the community to help improve the codebase and make it even better and simpler! Whether it's fixing bugs, adding new features, improving documentation, or enhancing performance, your contributions can make a significant impact on the project.

If you encounter a bug or have a feature request, we recommend using [GitHub's issue tracker](https://github.com/hector-munachi/rsl-component-v/issues/new/choose) to report it. This allows us to track issues and prioritize them accordingly. Please be sure to provide a clear and detailed description of the issue, including any error messages or screenshots that may be helpful.

If you would like to contribute code changes, please follow these steps:

1. Fork the repository and create a new branch for your changes.
2. Make your changes and ensure that all tests pass.
3. Create a pull request on GitHub with a description of your changes and the problem they solve.

We will review your changes and provide feedback as needed. Thank you for your contributions!



## Acknowledgements

`InputRSLV` component was built with Vite and Vue 3. It uses pre-defined data for regions, states, and LGAs in Nigeria. The original code was provided by the user.
## Spread the word

If you find our npm package useful, please help us spread the word! Share it with your colleagues, friends, and the wider community. This can help us attract more contributors and improve the project's visibility.

We appreciate your contributions in making our npm package better and simpler! Thank you for your support.


## License

This project is licensed under the [MIT](https://choosealicense.com/licenses/mit/) License. 

