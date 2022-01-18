methods: {
    mousemove (e) {
      let mouseX = e.clientX;
      let mouseY = e.clientY;

      let products = document.querySelectorAll('.products .product');
      for (let i = 0; i < products.length; i++) {
        let product = products[i];

        let product_image = product.querySelector('.product-image-wrap');

        let img_x = mouseX - this.coords(product_image).x;
        let img_y = mouseY - this.coords(product_image).y;

        product_image.style.transform = `translateY(-${img_y/40}px) translateX(-${img_x/40}px) translateZ(100px)`;
      }
    },
    coords (el) {
      let coords = el.getBoundingClientRect();
      return {
        x: coords.left / 2,
        y: coords.top / 2
      }
    }
  }
}