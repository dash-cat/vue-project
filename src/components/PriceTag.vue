<template>
  <!-- <div class="price-tag">
    <div class="header d-flex justify-content-between">
      <div class="date">{{ currentDate }}</div>
      <div class="company">{{ companyName }}</div>
    </div>
    <div class="name mb-2">{{ product?.print_name || product?.name }}</div>
    <div class="price mt-auto d-flex justify-content-between align-items-start">
      <div class="price-item d-flex">
        <div class="price-total">{{ priceMain }}</div>
        <div class="price-info">
          <div class="price-part">{{ pricePart }}</div>
          <div class="currency">₽/{{ measurement }}</div>
        </div>
      </div>
      <div class="price-qr">
        <qrcode :value="qrcode" size="35" />
      </div>
    </div>

    <div class="bottom">
      <div class="barcode-item">
        <div>Артикул: {{ product?.articul }}</div>
        <div class="barcode-row">
          <div class="barcode">
            <template v-if="product?.package?.[0]?.barcode?.barcode">
              <div class="barcode-body">
                <img
                  style="height: 50px"
                  alt="Barcode Generator TEC-IT"
                  :src="getUrlBarcode"
                  class="bcode-img"
                />
              </div>
            </template>
          </div>

          <div class="info" style="flex: 1">
            <div class="country">Страна: {{ product?.country?.name }}</div>
            <div class="manufacturer">
              Производитель: {{ product?.manufacturer?.name }}
            </div>
            <div v-if="plus" class="manufacturer">PLU: {{ plus }}</div>
          </div>
        </div>
      </div>
    </div> 
  </div> -->
  <div>
  <div>
    <div class="price-tag">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/profitable.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
  </div>
  <div>
    <div class="price-tage">
      <div class="header">
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/two.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
      </div>
      <div class="body">
        <div class="line-green">
            <img src="../assets/bold.svg">
            <div class="za">за</div>
            <div class="price-o">
          <div class="one-price">{{ priceMain }} {{ pricePart }} руб</div>
           </div>
        </div>
         <div class="description">
            <div class="name-product"> {{ product?.print_name || product?.name }} chips</div>
            <div class="last-price">
              <div>Старая цена за</div>
              <div>ШТ (руб.)</div>
            </div>
            <div class="across">{{ priceMain }}</div>
            <div class="country">{{ product?.country?.name }} ru</div>
         </div>
         <div class="down">
          <img src="../assets/down.svg">
          <div class="barecode">shtrix</div>
          <div class="manuf">{{ product?.manufacturer?.name }} ru</div>
         </div>
      </div>
    </div>
  </div>
    <div class="mini-tag">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/mini-left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/fasole.svg " >
        <img class="rigth-line" src="../assets/mini-rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="last-price">Цена: за шт</div>
        <div class="price-now"> {{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
    <div>
      <div class="mini-hei">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/mini-left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/fasole.svg " >
        <img class="rigth-line" src="../assets/mini-rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="price-now"> {{ priceMain }} {{ pricePart }}</div>
        <div class="last-price">Цена: за шт</div>
        <div class="barecode"></div>
        <div class="artic">artic</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="date"> data </div>

      </div>
    </div>
    </div>
    <div> 
      <div class="maxi-hey">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/mini-left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/fasole.svg " >
        <img class="rigth-line" src="../assets/mini-rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="price-now"> {{ priceMain }} {{ pricePart }}</div>
        <div class="last-price">Цена: за шт</div>
        <div class="barecode"></div>
        <div class="box">
        <div class="artic">artic</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="date"> data </div>
        </div>
      </div>
    </div></div>
    <div>
        <div>
    <div class="price-ta">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/sale.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
  </div>
      <div class="price-t">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/adder.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
    </div>
      <div class="price-">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/super.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
      <div class="price-right">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/two.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
    <div class="price-right-two">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/choose.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
        <div class="price-right-thee">
      <div class="header">
      <div class="description">{{ product?.manufacturer?.name }}</div>
        <img class="left-line" src="../assets/left.svg">
        <img src="../assets/cart.svg" class="cart" style="z-index: 1">
        <img class="adds" src="../assets/catch.svg " >
        <img class="rigth-line" src="../assets/rigth.svg">
        <img src="../assets/line.svg" class="line"> 
      </div>
      <div class="body">
        <div class="item">{{ product?.print_name || product?.name }} name</div>
        <div class="country"> {{ product?.country?.name }} Россия </div>
        <div class="midle-element">
        <div class="last-price">Старая цена за</div>
        <div class="last-price">ШТ (руб.)</div>
        <div class="last-price-left">Цена за</div>
        <div class="last-price-left">ШТ (руб.)</div>
        </div>
        <div class="crossed-out">88</div>
        <img src="../assets/line-down.svg" class="green-body"/>
        <img src="../assets/orange.svg" class="orange"/>
        <div class="price">{{ priceMain }} {{ pricePart }}</div>
        <div class="barecode"></div>
      </div>
    </div>
  </div>
</template>

<script>

  export default {
    props: {
      product: Object,
      default: () => {},
      weight_format: String
    },

    data: () => ({
      currentDate: new Date()
    }),

    mounted() {},

    computed: {
      
      getUrlBarcode() {
        const barcode = this.getBarcode(this.product)
        // let type = 'EAN13'
        // if (barcode.length === 8) type = 'EAN8'
        return `https://barcode.tec-it.com/barcode.ashx?data=${barcode}`
      },
      priceMain() {
        let price = this.product?.retailPrice || 0
        if (
          this.weight_format === 'gram' &&
          this.product.measurement?.name === 'КГ.'
        )
          price /= 10
        return Math.trunc(price)
      },
      pricePart() {
        let price = this.product?.retailPrice || 0
        if (
          this.weight_format === 'gram' &&
          this.product.measurement?.name === 'КГ.'
        )
          price /= 10
        return (+price % 1).toFixed(2).split('.')[1]
      },
      qrcode() {
        const barcode = this.product?.package?.[0]?.barcode?.barcode || '-'
        const article = this.product?.articul || '-'
        const price = this.product?.retailPrice.toFixed(2) || '-'

        return `${barcode} ${article} ${price}`
      },
      measurement() {
        if (
          this.weight_format === 'gram' &&
          this.product.measurement?.name === 'КГ.'
        )
          return '100г'
        return this.product?.measurement?.name?.toLowerCase()
      },
      plus() {
        return this.product?.plu
          ?.slice(0, 5)
          .map((el) => el.plu)
          .join(',')
      }
    },

    methods: {
      getBarcode(product) {
        let barcode = product.package[0].barcode.barcode
        if (['КГ.'].includes(product.measurement?.name)) {
          barcode += '01000'
          return barcode + this.getCheckSum(barcode)
        }
        return barcode
      },
      getPrice(product) {
        return product.retailPrice
      },
      getCheckSum(ean) {
        if (!ean || ean.length !== 12) return ''
        const multiply = [1, 3]
        let total = 0
        ean.split('').forEach((letter, index) => {
          total += parseInt(letter, 10) * multiply[index % 2]
        })
        const base10Superior = Math.ceil(total / 10) * 10
        return base10Superior - total
      }
    }
  }
</script>

<style lang="scss" scoped>
  .price-tag {
  position: absolute;
  width: 651px;
  height: 389px;
  left: 60px;
  top: 80px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price-tage {
     position: absolute;
     width: 651px;
     height: 389px;
     left: 850px;
     top: 80px;
     background: #FFFFFF;
     border: 2px solid #000000;
     .adds {
         position: absolute;
         width: 390.98px;
         height: 53px;
         left: 130.51px;
         top: 23px;
         color: #F17D00;
    }
     .cart{
         position: absolute;
         left: 4.05%;
         right: 3.51%;
         top: 6.01%;
         bottom: 3.34%;
    }
     .bold {
         position: absolute;
         width: 651px;
         height: 114px;
         left: 0px;
         top: 76px;
    }
     .rigth-line {
         position: absolute;
         width: 80px;
         height: 4px;
         left: 571px;
         top: 66px;
    }
     .left-line {
         position: absolute;
         width: 30px;
         height: 4px;
         left: 0px;
         top: 66px;
    }
}
 .body{
     .line-green {
         position: absolute;
         width: 651px;
         height: 114px;
         left: 0px;
         top: 76px;
         .za {
             position: absolute;
             width: 50px;
             height: 54px;
             left: 38px;
             top: 34.77px;
             font-family: 'Arial';
             font-style: normal;
             font-weight: 700;
             font-size: 47.2263px;
             line-height: 54px;
             display: flex;
             align-items: center;
             text-align: center;
             letter-spacing: 0.015em;
             color: #000000;
        }
         .price-o {
             display: flex;
             flex-direction: row;
             align-items: flex-end;
             padding: 0px;
             gap: 7px;
             position: absolute;
             width: 298.03px;
             height: 62.25px;
             left: 176px;
             top: 26px;
             .one-price {
                 position: absolute;
                 font-family: 'Arial';
                 font-style: normal;
                 font-weight: 700;
                 font-size: 47.2263px;
                 line-height: 54px;
                 display: flex;
                 align-items: center;
                 text-align: center;
                 letter-spacing: 0.015em;
                 color: #000000;
                 text-wrap: nowrap;
            }
         }
     }
             .description {
                 .name-product {
                     position: absolute;
                     width: 201px;
                      height: 17px;
                     left: 38px;
                     top: 204px;
                     font-family: 'Tahoma';
                     font-style: normal;
                     font-weight: 700;
                     font-size: 14.5889px;
                      line-height: 17px;
                     display: flex;
                     align-items: center;
                     text-align: center;
                     letter-spacing: 0.015em;
                     color: #000000;
                }
                .last-price {
                  display: flex;
                  flex-direction: row;
                  align-items: flex-start;
                  padding: 0px;
                  gap: 20px;
                  text-wrap: nowrap;
                  position: absolute;
                  width: 201px;
                  height: 17px;
                  left: 399px;
                  top: 197px;
                }
              .across {
                position: absolute;
                width: 132px;
                height: 55px;
                left: 434px;
                top: 222px;
                font-family: 'Ubuntu';
                font-style: normal;
                font-weight: 700;
                font-size: 47.4961px;
                line-height: 55px;
                display: flex;
                align-items: center;
                text-align: center;
                text-decoration-line: line-through;
                color: #808080;
              }
              .country {
                position: absolute;
                width: 110px;
                height: 29px;
                left: 367px;
                top: 282px;

                font-family: 'Arial';
                font-style: normal;
                font-weight: 400;
                font-size: 25.3004px;
                line-height: 29px;
                /* identical to box height */

                display: flex;
                align-items: center;

                color: #000000;
              }
            }
    .down {
      position: absolute;
      width: 651px;
      height: 78px;
      left: 0px;
      top: 311px;

      .barecode {
        position: absolute;
        width: 201px;
        height: 73px;
        left: 33px;
        top: 0px;

      }
      .manuf {
        position: absolute;
        width: 328px;
        height: 18px;
        left: 287px;
        top: 28px;
        font-family: 'Arial';
        font-style: normal;
        font-weight: 400;
        font-size: 15.7705px;
        line-height: 18px;
        display: flex;
        align-items: center;
        color: #000000;
      }
    }
 }

.mini-tag {
  position: absolute;
  width: 200px;
  height: 140px;
  left: 850px;
  top: 496px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .description {
    position: absolute;
    width: 101px;
    height: 6px;
    right: 4.07px;
    top: 1.54px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 4.84499px;
    line-height: 6px;
    display: flex;
    align-items: center;
    color: #000000;
  }

  .adds {
  position: absolute;
  width: 113.55px;
  height: 28.04px;
  left: calc(50% - 113.55px/2 + 11.83px);
  top: calc(50% - 28.04px/2 - 47.07px);
  border: 1.04425px solid #FFFFFF;
  }

  .cart{
  position: absolute;
  left: 4.05%;
  right: 3.51%;
  top: 6.01%;
  bottom: 3.34%;
  height: 27px;
  width: 32px;

  }

  .line {
  position: absolute;
  width: 200px;
  height: 7.37px;
  left: calc(50% - 200px/2);
  top: calc(50% - 7.37px/2 - 31.29px);


  }
  .rigth-line {
  position: absolute;
  width: 27.04px;
  height: 1.23px;
  right: 0px;
  top: 31.95px;
  }
  
  .left-line {
  position: absolute;
  width: 17.51px;
  height: 4px;
  left: 0px;
  top: 30px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 145.56px;
    height: 28px;
    left: calc(50% - 145.56px/2 - 0.08px);
    top: calc(50% - 28px/2 - 12.37px);
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 11.5714px;
    line-height: 14px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
    position: absolute;
    width: 28px;
    height: 7px;
    left: calc(50% - 28px/2 + 0.33px);
    bottom: 3.66px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 6.38556px;
    line-height: 7px;
    display: flex;
    align-items: center;
     color: #000000;
  }

  .last-price {
  position: absolute;
  width: 36px;
  height: 7px;
  left: 12px;
  bottom: 41px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 6.38556px;
  line-height: 7px;
  display: flex;
  align-items: center;
  text-wrap: nowrap;
  color: #000000;
  }

  .price-now {
    position: absolute;
    width: 100px;
    height: 29px;
    right: 18.28px;
    bottom: 16px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 700;
    font-size: 25.4446px;
    line-height: 29px;
    display: flex;
    align-items: center;
    text-align: center;
    color: #000000;
  }
  
  .baracode {
    position: absolute;
    width: 43.01px;
    height: 19.66px;
    left: 12.29px;
    bottom: 16.34px;

  }

}
}

.mini-hei {
  position: absolute;
  width: 100px;
  height: 140px;
  left: 1064px;
  top: 496px;
  background: #FFFFFF;
  border: 2px solid #000000;


  .description {
    position: absolute;
    width: 79px;
    height: 4px;
    right: 2px;
    top: 3px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 3.78965px;
    line-height: 4px;
    display: flex;
    align-items: center;
    color: #000000;

  }

  .adds {
  position: absolute;
  left: 24.85%;
  right: 0%;
  top: 6.52%;
  bottom: 14.97%;
  width: 61.99px;
  height: 15.31px;
  border: 0.570117px solid #FFFFFF;
  }

  .cart{
  position: absolute;
  width: 15.93px;
  height: 19.5px;
  left: 8px;
  top: 7px;

  }

  .line {
  position: absolute;
  width: 96px;
  height: 5px;
  left: 0;
  top: calc(50% - 5px/2 - 43.5px);
  right: 0;
  }
  .rigth-line {
  position: absolute;
  width: 7px;
  height: 1px;
  right: 0px;
  top: 20px;
  }
  
  .left-line {
  position: absolute;
  width: 17.51px;
  width: 10px;
  height: 1px;
  left: 0px;
  top: 20px;

  }


  

  .body {
    .item {
    position: absolute;
    width: 91px;
    height: 36px;
    left: calc(50% - 91px/2 + 0.5px);
    top: calc(50% - 36px/2 - 21px);

    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 9.94731px;
    line-height: 12px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .last-price {
    position: absolute;
    width: 23px;
    height: 5px;
    left: 7px;
    bottom: 31px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 700;
    font-size: 3.92px;
    line-height: 5px;
    display: flex;
    align-items: center;
    color: #000000;
  }

  .price-now {
    position: absolute;
    width: 74px;
    height: 17px;
    left: 24px;
    bottom: 37px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 700;
    font-size: 14.7579px;
    line-height: 17px;
    display: flex;
    align-items: center;
    text-align: center;
    color: #000000;
  }
  
  .baracode {
    position: absolute;
    width: 25px;
    height: 12px;
    left: 7px;
    bottom: 18px;
  }

 
    

    .country {
    position: absolute;
    width: 28px;
    height: 7px;
    left: calc(50% - 28px/2 + 0.33px);
    bottom: 3.66px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 6.38556px;
    line-height: 7px;
    display: flex;
    align-items: center;
    color: #000000;
  }

  .date {
    position: absolute;
    width: 20px;
    height: 5px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 3.92205px;
    line-height: 5px;
    bottom: 3.66px;
    color: #000000;
    left: 2px;
    bottom: 2px;

  }

  .artic {
    position: absolute;
    width: 20px;
    height: 5px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 3.92px;
    line-height: 5px;
    display: flex;
    align-items: center;
    color: #000000;
    right: 2px;
    bottom: 2px;

  }
  }
}

.maxi-hey {
  position: absolute;
  width: 200px;
  height: 280px;
  left: 1184px;
  top: 496px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .description {
  position: absolute;
  width: 154px;
  height: 8px;
  right: 6px;
  top: 3px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 7.3828px;
  line-height: 8px;
  display: flex;
  align-items: center;
  color: #000000;

  }

  .adds {
  position: absolute;
  height: 29.828611373901367px;
  width: 120.76860809326172px;
  left: 39.93017578125px;
  top: 2.47607421875px;
  border-radius: 0px;
  left: 24.85%;
  right: 0%;
  top: 6.52%;
  bottom: 14.97%;

  }

  .cart{
    position: absolute;
    width: 31.04px;
    height: 37.99px;
    left: 22.53px;
    top: 12.74px;

  }

  .line {
    position: absolute;
    width: 196px;
    height: 9.74px;
    left: 0px;
    top: calc(50% - 9.74px/2 - 91.22px);
  }
  .rigth-line {
  position: absolute;
  width: 13.64px;
  height: 1.95px;
  right: 0.19px;
  top: 40.01px;
  }
  
  .left-line {
  position: absolute;
  width: 19.48px;
  height: 1.95px;
  left: 0px;
  top: 40.01px;

  }

  .body {
    .item {
    position: absolute;
    width: 177.28px;
    height: 69px;
    left: calc(50% - 177.28px/2 + 3.38px);
    top: calc(50% - 69px/2 - 47.95px);

    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 19.3788px;
    line-height: 23px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;

    color: #000000;
    }

    .price-now {
    position: absolute;
    width: 181px;
    height: 41px;
    left: 13px;
    bottom: 68.3px;

    font-family: 'Arial';
    font-style: normal;
    font-weight: 700;
    font-size: 35.985px;
    line-height: 41px;
    display: flex;
    align-items: center;
    text-align: center;

    color: #000000;
  }

  .last-price {
    position: absolute;
    width: 44px;
    height: 9px;
    left: 76px;
    bottom: 50px;

    font-family: 'Arial';
    font-style: normal;
    font-weight: 700;
    font-size: 7.63674px;
    line-height: 9px;
    display: flex;
    align-items: center;
    color: #000000;
    text-wrap: nowrap;
  }
  
  .baracode {
    position: absolute;
    width: 48.7px;
    height: 23.38px;
    left: 76px;
    bottom: 23.93px;
  }
    .box{
      display: flex;

    .country {
    position: absolute;
    width: 28px;
    height: 7px;
    left: calc(50% - 28px/2 + 0.33px);
    bottom: 6px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 6.38556px;
    line-height: 7px;
    display: flex;
    align-items: center;
    color: #000000;
  }

  .date {
    position: absolute;
    width: 20px;
    height: 5px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 3.92205px;
    line-height: 5px;
    bottom: 6px;
    color: #000000;
    left: 6px;

  }

  .artic {
    position: absolute;
    width: 20px;
    height: 5px;
    font-family: 'Arial';
    font-style: normal;
    font-weight: 400;
    font-size: 3.92px;
    line-height: 5px;
    display: flex;
    align-items: center;
    color: #000000;
    right: 6px;
    bottom: 6px;
  }
    }
  }
}

.price-ta {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 60px;
  top: 832px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price-t {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 60px;
  top: 1277px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price- {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 60px;
  top: 1763px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price-right {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 850px;
  top: 832px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 315.07px;
  height: 52.39px;
  left: 168px;
  top: 23.92px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price-right-two {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 850px;
  top: 1277px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}

.price-right-thee {
  box-sizing: border-box;
  position: absolute;
  width: 651px;
  height: 389px;
  left: 850px;
  top: 1763px;
  background: #FFFFFF;
  border: 2px solid #000000;

  .adds {
  font-size: 40px;
  position: absolute;
  width: 423px;
  height: 53px;
  left: 114px;
  top: 23px;
  color: #F17D00;
  }
  .cart{
  position: absolute;
  width: 67px;
  height: 82px;
  left: 29px;
  top: 4px;

  }

  .line {
  position: absolute;
  width: 647px;
  height: 24px;
  left: 0px;
  top: 76px;

  }
  .rigth-line {
  position: absolute;
  width: 80px;
  height: 4px;
  left: 567px;
  top: 66px;
  }
  
  .left-line {
  position: absolute;
  width: 30px;
  height: 4px;
  left: 0px;
  top: 66px;
  }

  .description {
  position: absolute;
  width: 328px;
  height: 18px;
  left: 162px;
  top: 5px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 15.7705px;
  line-height: 18px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  

  .body {
    .item {
    position: absolute;
    width: 502px;
    height: 31px;
    left: 75px;
    top: 112px;
    font-family: 'Tahoma';
    font-style: normal;
    font-weight: 700;
    font-size: 25.9953px;
    line-height: 31px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: 0.015em;
    color: #000000;
    }

  .country {
  position: absolute;
  width: 110px;
  height: 29px;
  left: 10px;
  top: 175px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 25.3004px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }

  .last-price {
  width: 105px;
  height: 17px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 400;
  font-size: 14.5889px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .midle-element{
  white-space: nowrap;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  position: absolute;
  width: 538px;
  height: 29px;
  left: 33px;
  top: 205px;
  }
  .last-price-left {
  width: 95px;
  height: 29px;
  font-family: 'Arial';
  font-style: normal;
  font-weight: 700;
  font-size: 25.0016px;
  line-height: 29px;
  display: flex;
  align-items: center;
  color: #000000;
  }
  .crossed-out {
  position: absolute;
  width: 132px;
  height: 55px;
  left: 69px;
  top: 243px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 47.4961px;
  line-height: 55px;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration-line: line-through;
  color: #008000;

  }

.orange {
  position: absolute;
  width: 381px;
  height: 126px;
  left: 266px;
  top: 249px;
}

.price {
  position: absolute;
  width: 217px;
  height: 99px;
  left: 352px;
  top: 266px;
  font-family: 'Ubuntu';
  font-style: normal;
  font-weight: 700;
  font-size: 85.9843px;
  line-height: 99px;
  display: flex;
  align-items: center;
  text-align: center;
  color: #000000;
}
.barecode {
  position: absolute;
  width: 201px;
  height: 73px;
  left: 33px;
  top: 302px;
}
.green-body {
  position: absolute;
  width: 647px;
  height: 57px;
  left: 0px;
  bottom: 0;
}

}
}
</style>
