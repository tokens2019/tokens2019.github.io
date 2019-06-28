 

Rizwan Khan
Posted on 2019-04-27 00:32:17 187 Views  2 Likes
Large File Video Upload with Progress bar using jQuery Ajax and PHP
Large File Uplaod Tutorial using jQuery Ajax and PHP
Requirements are 

jQuery Library

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

jQuery Form Library for Progress Bar

https://cdnjs.cloudflare.com/ajax/libs/jquery.form/4.2.2/jquery.form.min.js


Hey guys watch the tutoriual and let me know how good it is.


And also visit our youtube channel and subscribe for new videos thanks...

Youtube Videos


Code

<script type="text/javascript">

		
		$(document).ready(function(){


			$("#upload-btn").on('click', function(){


				$("#file-upload").ajaxSubmit({

					beforeSubmit : function(formData, formObject, formOptions){

						formData.push(

							{name:'website', value: 'https://tokens2019.github.io
'},

							{name:'channel', value: 'https://www.youtube.com/rktutorial'},

						)


					},

					beforeSend : function(){


					},

					uploadProgress : function(event, position, total, percentComplete){

						$(".progress").css('width', percentComplete+'%');

						$('#progress').children("span").html(percentComplete+' %');


					},

					success: function(response){

						console.log(response)

						var resp = $.parseJSON(response)

						var htmlVideoTag = '<video width="490" height="350" controls>'+

  											'<source src="./uploads/'+ resp.message +'" type="video/mp4">'+

											  '<source src="mov_bbb.ogg" type="video/ogg">'+

											  'Your browser does not support HTML5 video.'+

											'</video>';



						$(".video-container").html(htmlVideoTag);						

					}

				});


			});			


		});


	</script>
