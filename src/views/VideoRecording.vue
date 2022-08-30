<template>
    <div >
        <div class="mt-5 mb-5">
            <input type="file" accept="video/*" v-on:change="videoFileUploaded($event)" id="videoFileUpload"> 
        </div>
        <div class="mt-4 mb-2">
            <video id="videoPreview" name="videoPreview"  v-show="file != ''" controls></video>
        </div>

        <!-- <t-button name="videoUploadBtn" type="button"> Upload Video </t-button> -->
    </div>
</template>
<script>



export default ({
    data(){
        return{
            file:''
        }
    },
    methods:{
        videoFileUploaded(event){
                console.log( "File Object ",event.target.files[0])
                //console.log( "Stream Object ",event.target.files[0].stream)
                this.file = event.target.files[0]
                this.videoPreview()
        },
        videoPreview(){
            let video= document.getElementById('videoPreview')
            let blobvar = URL.createObjectURL(this.file)
            console.log('File Reader iS Reading BOLB Created')
            video.src = blobvar
            console.log('Video done')
            //let videoInput = document.getElementById('videoFileUpload')
            //let fileReader = new FileReader()
            // fileReader.readAsDataURL(this.file)
            // console.log('File Reader iS Reading')
            // video.addEventListener('load' , function(){
            //     console.log("FIle Result onload called , ",fileReader.result)
            //     video.src = fileReader.result
            //     video.src = blobvar

            // })
           


        }

    }
})
</script>
