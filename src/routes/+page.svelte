<script>
	import ProjectCard from '../lib/components/projectcard.svelte';
	import ExperienceCard from '$lib/components/experiencecard.svelte';

	// images
	import GamedevTvThumbnail from '$lib/images/WorldsOfTheFuture/GamedevTV-Post.png';
	import WarboundThumbnail from '$lib/images/Warbound/WarboundThumbnail.gif';
	import WOTFThumbnail from '$lib/images/WorldsOfTheFuture/WorldsOfTheFutureThumbnail.gif';
	import CollegeSpitfireDemo from '$lib/images/SpitfireDemo/SpitfireDemoThumbnail.gif';
	import CollegeTowerDefense from '$lib/images/TowerDefense/TowerDefenseThumbnail.gif';
	import CollegeProjectShuffle from '$lib/images/ProjectShuffle/ProjectShuffleThumbnail.gif';
	import ProfilePicture from '$lib/images/pfp.jpg';

	// icons
	import Github from '$lib/icons/brand-github.svelte';
	import Youtube from '$lib/icons/brand-youtube.svelte';
	import Bluesky from '$lib/icons/brand-bluesky.svelte';
	import Linkedin from '$lib/icons/brand-linkedin.svelte';
	import Share from '$lib/icons/share.svelte';
	import Mail from '$lib/icons/mail-up.svelte';
</script>

<div class="split">
	<div class="fixed-wrapper">
		<div class="fixed">
			<div class="namecard">
				<img
					src={ProfilePicture}
					alt="Joshua staring towards the camera forcing a smile knowing full well he has been debugging code for 3 Days straight to find out perforce has not pushed everything to the repo."
					class="pfp"
					draggable="false"
				/>
				<div style="font-size: 1.75rem;">Joshua Pickering</div>
				<div style="font-size: 1rem; color: #E2BE73">Software Developer, Gameplay Programmer, Maker</div>
				<div class="socials">			
					<a href="https://youtube.com/@EncodicUE"><Youtube /></a>
					<a href="https://github.com/Encodic">
						<Github />
					</a>
					<a href="https://www.linkedin.com/in/joshua-pickering-3752b6178/">
						<Linkedin />
					</a>
					<a href="mailto:pickeringjoshua1999@gmail.com">
						<Mail />
					</a>
					<button
						class="share-button"
						on:click={() => {
							if (navigator.share) {
								navigator
									.share({
										title: "Joshua's Links",
										text: "Share a quick link to Josh's portfolio and socials",
										url: 'https://linktr.ee/Encodic'
									})
									.then(() => console.log('Shared successfully'))
									.catch(() => {
										console.log('Encountered an error while sharing');
									});
							} else {
								window.open('https://linktr.ee/Encodic');
							}
						}}
					>
						<Share />
					</button>
				</div>
			</div>
		</div>
	</div>
	<div class="scrolling">
		<h2 style= "color: #E2BE73">About Me</h2>
		<div>
			I'm a developer with history in games and software spanning over multiple years. <br /><br />
			I studied Art and Design at college focusing on Game Design and Development, since then heavily self taught gaining experience on personal and professional projects. During college I had work experience as a Game Tester at <a style = "color: #E2BE73" href="#dumplingdesign">Dumpling Design</a> aiding future updates to their mobile game 'Smash Tanks!'.<br /><br />
			My first ever big project was the freelance work I've done for <a style = "color: #E2BE73" href="#moonmengames">Moonmen Games</a> on '<a style = "color: #E2BE73" href="#worldsofthefuture">Worlds Of The Future</a>' an epic open world sci game. I also had the privilege to write a blog post about that project on <a style = "color: #E2BE73" href="https://www.gamedev.tv/articles/creating-an-open-world-space-game">GameDev.tv</a>. During that time I was also working my first
			software development job at <a style = "color: #E2BE73" href="#dhp11">Dhp11 LTD</a> working on a 3D Telecommunication planning software to aid clients with an accurate 3D representation of their Telecommunication sites utilizing the power of Unreal Engine. <br/><br/>

		</div>
		<h2 style= "color: #E2BE73">Work Experience</h2>
		<div class="experience">
			<ExperienceCard
				Title="Moonmen Games"
				date="2018 - Present"
				Role="Freelance Developer"
				url="https://moonmengames.com/"
				id="moonmengames"
				Description="Working on 'Worlds Of The Future' by developing assets and gameplay systems including a Custom A* path finding solution for space ship interiors, procedural station generator and more. Also wrote a blog post on GameDev.tv"
				/>
			<ExperienceCard
				Title="Dhp11 LTD"
				date="2018 - 2020"
				Role="Software Developer & BIM Technician"
				url="https://www.dhp11.com"
				id="dhp11"
				Description="Worked with clients to develop and integrate telecommunication components for our telecommunication planning application Oasis 3D (Originally called TIDBO), whilst also providing updates and hotfixes to the application itself. Also lead development on some projects related to the application."
			/>
			<ExperienceCard
				Title="Dumpling Design"
				date="Winter 2017"
				Role="QA Tester - Work Experience"
				url="http://dumplingdesign.com"
				id="dumplingdesign"
				Description="Provided feedback and ideas to the development team at Dumpling Design aiding with bug fixing and feature testing by doing Quality Assurance for their mobile game 'Smash Tanks!'."
			/>
		</div>
		<button
			class="resume"
			on:click={() => {
				window.open('resume.pdf');
			}}>find more employment details on my <u style = "color: #E2BE73">resume</u></button
		>
		<h2 style= "color: #E2BE73">Projects</h2>
		<div class="projects">
			<ProjectCard
				Image={WarboundThumbnail}
				Alt="Image"
				Title="Warbound"
				Description="A WW2 multiplayer FPS/RTS. Currently in development in Unreal Engine 5."
				Skills="Unreal Engine, UE Blueprints, C++, Perforce, Figma, Blender"
				slug="warbound"
				id="warbound"
			/>
			<ProjectCard
				Image={WOTFThumbnail}
				Alt="Image"
				Title="Worlds Of The Future"
				Description="A vibrant open world sci-fi action/adventure. Currently in development in Unreal Engine 5."
				Skills="Unreal Engine, UE Blueprints, Blender"
				slug="https://www.youtube.com/watch?v=lfCZ2Qy3Duc"
				id="worldsofthefuture"
			/>	
			<ProjectCard
				Image={GamedevTvThumbnail}
				Alt="Image"
				Title="GameDev.tv Blog Post"
				Description="A blog post I made in 2021 for GameDev.tv who reached out to me about Worlds Of The Future."
				slug="https://www.gamedev.tv/articles/creating-an-open-world-space-game"
				Skills=""
				id="gamedevtvwotf"
			/>
			<ProjectCard
				Image={CollegeTowerDefense}
				Alt="Image"
				Title="FMP - Tower Defence Game"
				Description="My final major project for my college course. Made in Unreal Engine 4."
				Skills="Unreal Engine, UE Blueprints, Blender"
				slug="https://www.youtube.com/watch?v=8t6ss-kaheE"
				id="collegetowerdefense"
			/>
			<ProjectCard
				Image={CollegeSpitfireDemo}
				Alt="Image"
				Title="FMP - Spitfire Demo"
				Description="My first major project for my first year of college. Made in Unreal Engine 4."
				Skills="Unreal Engine, UE Blueprints, Blender"
				slug="https://www.youtube.com/watch?v=WMN-2pf0nn4"
				id="collegespitfiredemo"
			/>
			<ProjectCard
				Image={CollegeProjectShuffle}
				Alt="Image"
				Title="FMP - Project Shuffle"
				Description="My first project for my first year of college. Made in Gamemaker: Studio."
				Skills="Gamemaker: Studio, GML(Gamemaker Language)"
				slug=""
				id="collegeprojectshuffle"
			/>
		</div>

		<a href="https://github.com/Encodic/portfolio" class="acknowledgment">
			{'Built with ❤️  & SvelteKit'}
		</a>
	</div>
</div>

<style>
	.split {
		display: grid;
		grid-template-columns: min(40% - 15px, 500px) min(60% - 15px, 700px);
		position: relative;
		justify-content: center;
		margin-top: 10rem;

		@media screen and (max-width: 1000px) {
			display: flex;
			flex-direction: column;
			align-items: center;
			margin: 0 1rem;
		}
	}

	h2 {
		margin-top: 3rem;
	}

	a,
	a:visited,
	a:hover,
	a:active {
		color: inherit;
	}

	.fixed {
		position: fixed;
		display: flex;

		@media screen and (max-width: 1000px) {
			position: relative;
		}
	}

	.scrolling {
		display: flex;
		flex-direction: column;
	}

	.namecard {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		justify-content: center;
		align-items: center;

		@media screen and (max-width: 1200px) {
			margin: 3rem 0;
		}
	}

	.pfp {
		display: flex;
		height: 15rem;
		aspect-ratio: 1/1;
		border-radius: 100%;
		object-fit: cover;
	}

	.socials {
		display: flex;
		justify-content: center;
		gap: 1rem;
	}

	.socials :hover {
		color: #E2BE73;
	}

	.share-button {
		border: none;
		padding: 0;
		margin: 0;
		height: 24px;
		cursor: pointer;
		background: none;
		color: black;
		@media (prefers-color-scheme: dark) {
			color: white;
		}
	}

	.experience {
		display: flex;
		flex-direction: column;
		gap: 3rem;
	}

	.resume {
		border: none;
		cursor: pointer;
		width: max-content;
		background: none;
		color: #202020;
		margin: 2rem 0;

		@media (prefers-color-scheme: dark) {
			color: #a0a0a0;
		}
	}

	.projects {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.acknowledgment {
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 0.5rem 1rem;
		width: max-content;
		margin: 2rem auto;
		cursor: pointer;
		text-decoration: none;
		color: black;
		font-size: 14px;
		font-weight: 350;
		border-radius: 25px;
		background: linear-gradient(145deg, #d8d8d8, #f0f0f0);
		box-shadow:
			9px 9px 17px #cccccc,
			-9px -9px 17px #ffffff;

		@media (prefers-color-scheme: dark) {
			color: white;
			background: linear-gradient(145deg, #101010, #141414);
			box-shadow:
				9px 9px 17px #070707,
				-9px -9px 17px #1d1d1d;
		}
	}
</style>
