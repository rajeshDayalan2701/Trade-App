<template>
  <q-page class="q-px-xl q-py-lg bg-grey-12">
    <div class="text-primary text-h6 text-weight-medium">Create your first transfer agreement</div>

    <q-card class="q-my-md">
      <div class="text-h6 text-weight-medium q-mx-md q-pt-lg q-pb-sm agreement-header">Transfer Agreement #1</div>

      <div class="flex q-pa-md item-container" :class="{'child-full-width': $q.screen.lt.sm}">
        <div class="item">
          <div class="item-label text-secondary">Buyer's Email</div>
          <div class="item-value">albertyeong@email.com</div>
        </div>
        <div class="item">
          <div class="item-label text-secondary">Exporting To</div>
          <div class="item-value">Singapore</div>
        </div>
        <div class="item">
          <div class="item-label text-secondary">Invoice Amount</div>
          <div class="item-value">USD 20,000</div>
        </div>
      </div>

      <div class="flex q-pa-md buyer-details-container bg-grey-2 text-grey-6 shadow-5" :class="{'child-full-width': $q.screen.lt.sm}">
        <div class="item">
          <div class="item-label">Buyer Details</div>
          <div class="item-value edit-btn">Edit</div>
        </div>
        <div class="item">
          <div class="item-label">Company</div>
          <div class="item-value">Ting Hoe Trading Company Pte Ltd, Singapore</div>
        </div>
        <div class="item">
          <div class="item-label">Contact Person</div>
          <div class="item-value">Albert Yeong, albertyeong@email.com</div>
        </div>
      </div>

      <div class="bg-grey-2">
        <q-list bordered class="rounded-borders">
          <q-expansion-item
            expand-separator
            label="Product Details"
            class="q-py-sm product-details"
            caption="Please enter product details"
            default-opened
          >
            <q-card class="q-pb-md">
              <q-card-section>
                <div class="text-h6 text-grey-8">Upload your proforma Invoice</div>
              </q-card-section>
              <q-card-section>
                <q-file
                  v-model="files"
                  outlined
                  use-chips
                  multiple
                  accept=".jpg, image/*, .pdf, .csv"
                >
                  <template v-slot>
                    <div class="text-center">
                      <div class="drop-icon-section flex items-center justify-center">
                        <q-icon name="file_upload" size="lg" color="accent"/>
                        <div class="text-h6 text-accent">Drop Proforma Invoice here</div>
                      </div>
                      <div class="text-blue-grey-6 text-weight-medium q-my-sm">Or <span class="text-accent">Browse</span> from your computer</div>
                      <div class="text-blue-grey-4 caption-text q-mb-xl">Acceptable formats - .pdf, .jpg, .png, .csv</div>
                    </div>
                  </template>
                </q-file>
              </q-card-section>
              <div class="row justify-end q-mr-md">
                <q-btn
                  label="Next"
                  color="primary"
                  :disable="!files.length"
                />
              </div>
            </q-card>
          </q-expansion-item>

          <q-expansion-item
            expand-separator
            label="Shipping Information"
            disable
            class="q-py-sm"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-expansion-item
            expand-separator
            label="Release Condition"
            disable
            class="q-py-sm"
          >
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>

          <q-expansion-item label="Payment Details" disable class="q-py-sm">
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
        </q-list>
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageTransfer',
  data () {
    return {
      files: []
    }
  }
})
</script>

<style lang="scss">
  .agreement-header {
    border-bottom: 2px dotted $grey-5;
  }

  .item-container, .buyer-details-container {
    align-items: flex-start;
    justify-content: space-between;
    & .item {
      flex-basis: 30%;
    }
  }
  .item-container.child-full-width, .buyer-details-container.child-full-width {
    & .item {
      flex-basis: 100%;
      margin-bottom: 0.5rem;
    }
  }
  .item-label {
    font-size: 1.1rem;
    font-weight: 500;
  }

  .item-value {
    font-size: 1rem;
    margin-top: 4px;
  }
  .edit-btn {
    cursor: pointer;
    color: $secondary;
    font-weight: 500;
  }
  .q-expansion-item__container {
    // padding: 0.5rem 0;
    .q-item__label {
      font-size: 1.2rem;
      color: $primary;
      font-weight: 600;
    }
    .q-item__label--caption {
      color: $grey-8;
      font-size: 0.9rem;
      font-weight: 400;
      margin-top: 1rem;
    }
  }
  .q-field--outlined.q-field--highlighted .q-field__control::after {
    border: 2px dashed $accent;
  }
  .q-field--outlined.q-field .q-field__control::before {
    border: 1px dashed rgba(0, 0, 0, 0.24);
  }
  .q-field__control-container {
    flex-direction: column;
  }
  .q-file .q-field__native {
    justify-content: center;
  }
</style>