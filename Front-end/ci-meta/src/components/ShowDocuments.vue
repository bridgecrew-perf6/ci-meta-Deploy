<template>
    <div>
      <h2 class="text-center">Document {{collection}} {{folder}} - {{folderNumber}} {{shelfmark}}</h2>
      <div class="text-center">
        <i>Use the <b-icon icon="pencil-square" ></b-icon> button to edit the relative field. Press the <strong>Update</strong> button at the bottom to update the Document</i>
      </div>
      <b-container>
        <hr>
<!-- Doc Type -->
        <b-row>
          <b-col b-col>
            <p v-show="!editType">
              <strong>Document type &emsp;</strong>{{documentType}}
              <b-button variant="link" size="sm" @click="editType = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editType">
              <b-form-input v-model="documentType" maxlength="255" placeholder="Type" />
              <b-input-group-append>
                <b-button variant="info" @click="editType=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
<!-- Date -->
          <b-col b-col >
            <p v-show="!editDate">
              <strong>Date &emsp;</strong>{{date}}
              <b-button variant="link" size="sm" @click="editDate = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
              <b-input-group class="mt-3" v-show="editDate">
                <b-form-input type="date" v-model="date" placeholder="Date" />
                <b-input-group-append>
                  <b-button variant="info" @click="editDate=false">Update</b-button>
                </b-input-group-append>
              </b-input-group>
            </div>
          </b-col>
        </b-row>
        <b-row>
<!-- Archive -->
          <b-col b-col >
            <p v-show="!editArchive">
              <strong>Archive &emsp;</strong>{{archive}}
              <b-button variant="link" size="sm" @click="editArchive = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
              <b-input-group class="mt-3" v-show="editArchive">
                <b-form-input v-model="archive" maxlength="255" placeholder="Archive" />
                <b-input-group-append>
                  <b-button variant="info" @click="editArchive=false">Update</b-button>
                </b-input-group-append>
              </b-input-group>
            </div>
          </b-col>
<!-- Publication -->
          <b-col b-col >
            <p v-show="!editPublication">
              <strong>Publication &emsp;</strong>{{publication}}
              <b-button variant="link" size="sm" @click="editPublication = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
              <b-input-group class="mt-3" v-show="editPublication">
                <b-form-input v-model="publication" placeholder="Publication" />
                <b-input-group-append>
                  <b-button variant="info" @click="editPublication=false">Update</b-button>
                </b-input-group-append>
              </b-input-group>
            </div>
          </b-col>
        </b-row>
<!-- Real Id -->
        <b-row>
          <b-col b-col >
            <p v-show="!editCollection">
              <strong>Collection &emsp;</strong>{{collection}}
              <b-button variant="link" size="sm" @click="editCollection = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editCollection">
              <b-form-input v-model="collection" maxlength="255" placeholder="Collection" />
              <b-input-group-append>
                <b-button variant="info" @click="editCollection=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
          <b-col b-col >
            <p v-show="!editFolder">
              <strong>Folder &emsp;</strong>{{folder}}
              <b-button variant="link" size="sm" @click="editFolder = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editFolder">
              <b-form-input v-model="folder" maxlength="255" placeholder="Folder" />
              <b-input-group-append>
                <b-button variant="info" @click="editFolder=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
          <b-col b-col >
            <p v-show="!editFolderNumber">
              <strong>Folder Number &emsp;</strong>{{folderNumber}}
              <b-button variant="link" size="sm" @click="editFolderNumber = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editFolderNumber">
              <b-form-input v-model="folderNumber" maxlength="255" placeholder="Folder Number" />
              <b-input-group-append>
                <b-button variant="info" @click="editFolderNumber=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
          <b-col b-col >
            <p v-show="!editShelfmark">
              <strong>Shelfmark &emsp;</strong>{{shelfmark}}
              <b-button variant="link" size="sm" @click="editShelfmark = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editShelfmark">
              <b-form-input v-model="shelfmark" maxlength="255" placeholder="Shelfmark" />
              <b-input-group-append>
                <b-button variant="info" @click="editShelfmark=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
        </b-row>

        <hr>
<!-- Title -->
        <b-row>
          <b-col b-col>
            <p v-show="!editTitle">
              <strong>Title &emsp;</strong>{{title}}
              &emsp;&emsp;
              <b-button variant="link" size="sm" @click="editTitle = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editTitle">
              <b-form-input v-model="title" maxlength="255" placeholder="Title" />
              <b-input-group-append>
                <b-button variant="info" @click="editTitle=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
<!-- Incipit -->
          <b-col b-col>
            <p v-show="!editIncipit">
              <strong>Incipit &emsp;</strong>{{incipit}}
              &emsp;&emsp;
              <b-button variant="link" size="sm" @click="editIncipit = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editIncipit">
              <b-form-input v-model="incipit" maxlength="255" placeholder="Incipit" />
              <b-input-group-append>
                <b-button variant="info" @click="editIncipit=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
        </b-row>
<!-- Transcription -->
        <b-row>
          <b-col b-col>
            <p v-show="!editTranscription">
              <strong>Transcription &emsp;</strong>{{transcription}}
              &emsp;&emsp;
              <b-button variant="link" size="sm" @click="editTranscription = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editTranscription">
              <b-form-textarea rows="6" v-model="transcription" maxlength="255" placeholder="Transcription" />
              <b-input-group-append>
                <b-button variant="info" @click="editTranscription=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
          <b-col b-col>
            <insert-image :id="id" ref="images"/>
          </b-col>
        </b-row>
<!-- Language -->
        <b-row>
          <br>
          <b-col b-col>
            <p v-show="!editLanguage">
              <strong>Language &emsp;</strong>{{language}}
              &emsp;&emsp;
              <b-button variant="link" size="sm" @click="editLanguage = true">
                  <b-icon icon="pencil-square" ></b-icon>
              </b-button>
            </p>
            <div>
            <b-input-group class="mt-3" v-show="editLanguage">
              <b-form-input v-model="language" maxlength="255" placeholder="Language" />
              <b-input-group-append>
                <b-button variant="info" @click="editLanguage=false">Update</b-button>
              </b-input-group-append>
            </b-input-group>
            </div>
          </b-col>
        </b-row>

        <hr>

<!-- Places -->
        <b-row>
          <b-col>
            <show-edit-position :docId="id"/>
          </b-col>
        </b-row>
        <br>
<!-- Persons -->
        <b-row>
          <b-col>
            <show-edit-actor :docId="id"/>
          </b-col>
        </b-row>
        <br>
<!-- Note -->
        <b-row>
          <b-col>
            <p>
              <strong>Note &emsp;</strong>
            </p>
            <div>
            <b-input-group class="mt-3">
              <b-form-input prepend="Note" v-model="note" maxlength="255" />
            </b-input-group>
            </div>
            <br>
          </b-col>
        </b-row>

      </b-container>
      <div v-show="deleteConfirm">
        <br>
        <b-container>
          <b-card border-variant="danger"
            header="Delete Confirm"
            header-border-variant="danger"
            header-text-variant="danger"
          align="center">
            <b-card-text class="text-center">
              Are you sure you want to delete this document?&emsp;
              <b-button variant="danger" @click="deleteDocument(id)">Yes</b-button>&emsp;
              <b-button variant="success" @click="deleteConfirm = false">No</b-button>
            </b-card-text>
          </b-card>
        </b-container>
      </div>
        <br>
      <div class="text-center" v-show="!deleteConfirm">
        <b-button variant="danger" @click="deleteConfirm=true">Delete</b-button>&emsp;
        <b-button variant="success" @click="submit()">Update</b-button>
      </div>
  </div>
</template>

<script>
import InsertImage from './InsertImage.vue';
import ShowEditPosition from './ShowEditPosition.vue';
import ShowEditActor from './ShowEditActor.vue';
export default {
  components: { InsertImage, ShowEditPosition, ShowEditActor },
  name: 'ShowDocuments',
  props : ['id'],
  data () {
    return {
      documentType: '',
      incipit: '',
      transcription: '',
      language: '',
      date: '',
      isDateDeduced: false,
      collection: '',
      folder: '',
      folderNumber: '',
      shelfmark: '',
      note: '',
      title: '',
      archive: '',
      publication: '',
      error: false,
      editShelfmark: false,
      loading: false,
      success: false,
      editType: false,
      editIncipit: false,
      editTranscription: false,
      editLanguage: false,
      editDate: false,
      editDateDeduced: false,
      editCollection: false,
      editFolder: false,
      editFolderNumber: false,
      editArchive: false,
      editTitle: false,
      editPublication: false,
      deleteConfirm : false,
    }
  },
  async mounted() {
    try {
      this.error = false;
      const header = { 'Content-Type': 'application/json' };
      const response = await this.$http.get('http://'+this.$store.state.address+'/api/v1/document/'+this.id, header);
      if (response.status==200){
        this.show=true;
        this.documentType=response.data.result.type;
        this.incipit=response.data.result.incipit;
        this.transcription=response.data.result.transcription;
        this.language=response.data.result.language;
        this.date=response.data.result.gregorian_date;
        this.isDateDeduced=response.data.result.is_date_deduced;
        this.collection=response.data.result.collection;
        this.folder=response.data.result.folder;
        this.folderNumber=response.data.result.folder_number;
        this.shelfmark=response.data.result.shelfmark;
        this.note=response.data.result.note;
        this.title=response.data.result.title;
        this.archive=response.data.result.archive;
        this.publication=response.data.result.publication;
      }
    }
    catch (e) {
      this.loading = false;
      console.log(e);
      this.error = true;
    } 
  },
  methods: {
    async deleteDocument(id) {
      try {
        const header = { 'Content-Type': 'application/json' };
        const data = {'is_deleted': 'true'}
        const response = await this.$http.put('http://'+this.$store.state.address+'/api/v1/document/'+this.id, data, header);
        if (response.status==200)
          this.$router.push({name: 'Home'});
      }
      catch (e) {
        console.log(e);
      }
    },
    async submit() {
      try {
        this.$refs.images.submit();
        this.error = false;
        const data = { type: this.documentType, 
                      incipit: this.incipit,
                      transcription: this.transcription,
                      note: this.note,
                      language: this.language,
                      gregorian_date : this.date,
                      collection : this.collection,
                      shelfmark: this.shelfmark,
                      folder_number: this.folder_number,
                      is_date_deduced: this.isDateDeduced,
                      publication: this.publication,
                      archive: this.archive,
                      title: this.title};
        const header = { 'Content-Type': 'application/json' };
        this.loading=true;
        const response = await this.$http.put('http://'+this.$store.state.address+'/api/v1/document/'+this.id, data, header);
        if (response.status==200){
              this.$router.push({ name: 'Home'});
            }
      }
      catch (e) {
        console.log(e);
      }
    }
  }
};
</script>
