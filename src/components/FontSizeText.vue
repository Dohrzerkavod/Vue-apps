<template>
    <div :class="['mx-auto', fontClass]" :style="lineHeightStyle">
      {{ text }}
    </div>
  </template>
  
  <script>
  export default {
    name: 'FontSizeText',
    props: {
      text: {
        type: String,
        required: true
      }
    },
    computed: {
      fontClass() {
        const length = this.text.length;
        if (length <= 10) {
          return 'text-9xl'; // Updated largest font size
        } else if (length <= 30) {
          return 'text-8xl';
        } else if (length <= 70) {
          return 'text-7xl';
        } else if (length <= 100) {
          return 'text-6xl';
        } else  {
          return 'text-5xl';
        }
      },
      lineHeightStyle() {
        const fontSizeClass = this.fontClass;
        let fontSize = 1; // Default font size
        switch (fontSizeClass) {
          case 'text-9xl':
            fontSize = 8; // 8rem for text-9xl
            break;
            case 'text-8xl':
            fontSize = 6; // 6rem for text-8xl
            break;
            case 'text-7xl':
            fontSize = 4.5; // 4.5rem for text-7xl
            break;
            case 'text-6xl':
            fontSize = 3.75; // 3.75rem for text-6xl
            break;
            case 'text-5xl':
            fontSize = 3; // 3rem for text-5xl
            break;
        }
        return {
          lineHeight: `${1.6 * fontSize}rem`
        };
      }
    }
  };
  </script>
  
  <style scoped>
  </style>
  