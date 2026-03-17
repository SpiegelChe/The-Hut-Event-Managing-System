<script>
    import Header from '$lib/components/Header.svelte';
    import participantBg from '$lib/images/participant_portal.png';
    import staffBg from '$lib/images/staff_portal.png';
</script>

<svelte:head>
    <title>The Hut Event Managing System</title>
    <meta name="description" content="THCC data managing home page" />
</svelte:head>

<Header
    portalTitle=""
    showLogout={false}
/>

<section class="page">
    <!-- Left: Participants -->
    <div
        class="panel participants"
        style={`--participant-bg: url(${participantBg})`}
    >
        <div class="content">
            <a class="btn btn_participants" href="/login/participant">REGISTER</a>
            <p class="hint">Get involved in our fantastic events!</p>
            <h1>PARTICIPANTS</h1>
        </div>
    </div>

    <!-- Right: Staff -->
    <div
        class="panel staff"
        style={`--staff-bg: url(${staffBg})`}    
    >
        <div class="content">
            <h1>STAFF</h1>
            <p class="hint">Welcome back!</p>
            <a class="btn btn_staff" href="/login/staff">LOGIN</a>
        </div>
    </div>
</section>

<style>
	.page {
		position: fixed;
		top: 80px;   /* same as header height */
		left: 0;
		right: 0;
		bottom: 0;

		display: grid;
		grid-template-columns: 1fr 1fr; /* 50/50 split */
		overflow: hidden; /* prevent scrollbars */
	}

	.panel {
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		border: none;
		box-sizing: border-box;
	}

	.participants {
		color: #fff;
        background-image:
			linear-gradient(rgba(13, 95, 107, 0.35), rgba(13, 95, 107, 0.35)),
			var(--participant-bg);
		background-size: cover;
		background-position: center 60%;
		background-repeat: no-repeat;
	}

	.staff {
		color: #0d5f6b;
        background-image:
			linear-gradient(rgba(255, 255, 255, 0.4), rgba(255, 255, 255, 0.4)),
			var(--staff-bg);
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
	}

	.content {
		text-align: center;
		width: min(720px, 92%);
		padding: 20px;
		box-sizing: border-box;
	}

	h1 {
		margin: 0;
		font-weight: 900;
		letter-spacing: 0.03em;
		line-height: 1;
		white-space: nowrap;     /* keep one line */
		text-align: center;
	}

	.participants h1 {
		font-size: clamp(44px, 5.2vw, 74px);
	}

	.staff h1 {
		font-size: clamp(44px, 6.2vw, 86px);
	}

	.hint {
		margin: 18px 0 0;
		font-size: 15px;
		font-weight: 300;
		letter-spacing: 0.02em;
		opacity: 0.9;
	}

	.btn {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		min-width: 120px;
		height: 44px;
		padding: 0 18px;
		border-radius: 8px;
		text-decoration: none;
		font-weight: 900;
		letter-spacing: 0.06em;
	}

	.btn_participants {
		background: #b7f1c7;
		color: #0d5f6b;
		margin-bottom: 26px;
	}

	.btn_staff {
		background: #c55a1b;
		color: #fff;
		margin-top: 26px;
	}

	@media (max-width: 900px) {
		.page {
			grid-template-columns: 1fr;
		}
		h1 {
			font-size: 64px;
		}
	}

</style>