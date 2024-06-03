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
        } else if (length <= 20) {
          return 'text-8xl';
        } else if (length <= 30) {
          return 'text-7xl';
        } else if (length <= 40) {
          return 'text-6xl';
        } else if (length <= 50) {
          return 'text-5xl';
        } else if (length <= 60) {
          return 'text-4xl';
        } else if (length <= 70) {
          return 'text-3xl';
        } else if (length <= 80) {
          return 'text-2xl';
        } else {
          return 'text-xl';
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
            case 'text-4xl':
            fontSize = 2.25; // 2.25rem for text-4xl
            break;
            case 'text-3xl':
            fontSize = 1.875; // 1.875rem for text3xl
            break;
            case 'text-2xl':
            fontSize = 1.5; // 1.5rem for text-2xl
            break;
          case 'text-xl':
            fontSize = 1.25; // 1.25rem for text-xl
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
  