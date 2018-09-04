<template>
    <div id="app">
        <button
        type="button"
        class="btn"
        @click="showModal"
        >
        Open Modal!
        </button>

      
        <div class="card" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" 
                    class="btn btn-primary"
                    @click="showModal"
                >
                    Show Modal
                </a>
                <modal
                    v-show="isModalVisible"
                    @close="closeModal"
                />
            </div>
        </div>
    </div>
</template>

<script>
import modal from '~/components/modal';
export default {
    name: 'app',
    components: {
        modal,
    },
    data () {
      return {
        isModalVisible: false,
      };
    },
    methods: {
      showModal() {
        this.isModalVisible = true;
      },
      closeModal() {
        this.isModalVisible = false;
      }
    },
  };
</script>