# vashkar55.github.io
My Portfolio
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>My Portfolio</title>
	<style>
		.main {
			text-align: center;
			}
		.frame {
		  width: 300px;
		  height: 250px;
		  border: 3px solid #ccc;
		  background: #eee;
		  margin: auto;
		  padding: 15px 10px;
		}

	</style>
</head>
<body>
	<div id="Loading" style="text-align: center;">
		LOADING...
	</div>
	<div class="main" id="mainCont"  hidden >
	<img id="profileimage" class="frame">
	<h2 > Vashkar Karna </h2>
	<p id="bio"></p>
	<h5 id="followersinformation"></h5>
	<p>
		Check me on <a id="githublink">Github</a>
	</p>
	</div>
<script >
	fetch("https://api.github.com/users/vashkar55")
	.then(response=>response.json())
	.then(function(data)
	{
		console.log(data)
		let followersCount = data['followers']
		let followersInfo = `I have been followed by ${followersCount} people on github.`
		document.getElementById('profileimage').src = data['avatar_url']
		document.getElementById('bio').textContent = data['bio']
		document.getElementById('followersinformation').textContent = followersInfo
		document.getElementById('githublink').href = data['html_url']
		document.getElementById('mainCont').hidden = false
		document.getElementById('Loading').hidden = true
})
</script>

</body>
</html>
