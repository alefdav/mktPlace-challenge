<template>
  <div class="header">
    <header class="container padding-y">
      <div class="row d-flex justify-content-between align-items-center">
        <div class="col-6 col-sm-3 col-lg-2">
          <router-link to="/">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              width="143"
              height="25"
              viewBox="0 0 143 25"
            >
              <image
                id="logo"
                width="143"
                height="25"
                xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAAI8AAAAZCAYAAAAIXH3NAAAEh0lEQVRogeVby3HbMBBde9IAXYJ8SAFyCVQJ9CEFUCVIJYg3X8kCcpBKCEsIC/DBbIEdJBnYixloZxdYgB8x9pvhjIaWFgvg7Rfw3cvLCyyInBmqnXP4Pz+/Lzm/L4VvC0/2F/Pu7j9f8APzrrqBHovDkOcvM6jxBjulMjUAlMz7JUiRsnHcfCW0+FwAoBe+c0rQ4VPAhC1pMXeKkJIL3gQE8nBjjSFZUB4TtmLI46IBgCMADLE6fFbce+ZVK+bMWf6qcP/jdSp1SjSUbO1zXgo+8mwC5CiFBPgzYwsA5y82ZxG+sAXooh8ZV22s7y1ghasIWxZO+OJ+c2TeGaIUwrhuSP+yYStUbWXofejiljO77zOzcQNuWhfIW+jfNBspJbhbIVQZj5vaYihQrn1c2S3Or/Ek6BxyIhdwvTpFwm+RoYyC6CXqFPI8Fk8oADCcvSl+k+p5uOrNJY4kx6tHwPP4CFYy+Z/R4ylS3gaJuFFp/UFoziO62GK1p0kfjgEjOSt0u5Lhy3lcnITPU+MglP3PDnGWRiMsdixiPAngWvjW2npFbd55Eoogs96/laS+kiGRh7pk6xZzJpxM1SEuhcXaz92FXhCXyKEOwqZK4TQESuBtgKAcSssBiTycuzx5NncscsEq9oLl7zxNzB15xoLbvFgvYtFiCLY9I1fXiilMQPDEJ4E4jSNvT/RsmLDFyblgkWRC74OHC2LC3OFAbqnOLeJxxEJaSOWvRBwIeKKpvRRnMKkhtBWqV3C62bTpSkNkLoQqbr0axyipkW8ZOS2mCBYD8iBjuFD4cp4qQIx+ojY8534bD3GikXg4uhWqPhhJUI44rlxKTLrBnD6VZ732QnTgCCjtJ5v3+Ur1AT2L1BSbIlyB4H5jc4OxiKne+pHEtuXwxvEqPT4aUnLJesp6UfIMnvF7JLU7tpc8VqmWGegycxJbo3sfjYmvZAzErccgQ0PkLH6Dj6Zy4siTEkap0WaRRpRrSnXqYQZF/2EsQkcjtwDtNcVCIs6tkNJuuIKGPD0hSygXSgGXB0hlahQmOBi1838cQZyCIU6HXuzOqWyeFWvL6ZBChNF9M+1lsApLxmGGuyodWjS1zAzD1xTldgicJ+2cFv9YcJtLiTJgOlAGjIbmHoDkjNWzZ+Q8BBL6K2g7zIDha45wtfOEQq4pGQ2F96mYh6t8UsGRR/IwocYflxxLnXlwOshULpez+hqGGd2LGPK0MyXJlumd4NXqyE5qjaQrPRfV1gAu/zkoQpBE6hqfgsy/FjrSF8bLlMwZV+YQ8OwSTDoYjb1SoJUR+p501UM6JNSc7Yw9GA1BI086p3JPqgsPcai81OOJzvH0dsyU+0mGeM8xnmcJSOHrcIv/vJgQjefowR77xCS9NtlW5ycIqsclsV/3vu5rIw/gBLXxuLnhaXsMBmLxEqoIg2iV98wBx5WOe+x5mKaC7pG073LWSB7w3OyjvR+7KUdCot5ZlLXA6GfKfaqrPSg194NiCxIbhsxDL2vZjrFtM/i64vbMzRCMXhwzn62HMjp+JOwA8A+T/kDyZxz2GgAAAABJRU5ErkJggg=="
              />
            </svg>
          </router-link>
        </div>
        <div class="col-6 col-sm-3 col-lg-2">
          <nav>
            <ul>
              <li>
                <router-link to="/"> Produtos </router-link>
              </li>
              <li>
                <router-link to="/cart">
                  <div class="cartContainer">
                    <img src="../assets/icons/shopping-cart.svg" />
                    <span class="quantityBadge">{{ items }}</span>
                  </div>
                </router-link>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  computed: {
    items() {
      return this.$store.getters.quantityProductInCart;
    },
  },
};
</script>

<style lang="scss" scoped>
.header {
  box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.1);
}

svg {
  max-width: 100%;
}

nav {
  font-family: "SourceSansProBold", sans-serif;

  ul {
    display: flex;
    align-items: center;
    color: #909090;
    padding: 0;
    margin: 0 16px 0 auto;
    width: fit-content;

    li {
      cursor: pointer;

      img {
        max-width: 100%;
      }

      &:not(:first-child) {
        margin-left: 12px;
      }
    }
  }
}

.cartContainer {
  position: relative;

  .quantityBadge {
    font-size: 12px;
    color: #fff;
    background: red;
    border-radius: 50%;
    padding: 0 5px;
    position: absolute;
    right: -13px;
    bottom: 0;
  }
}
</style>