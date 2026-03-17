<script>
    import Header from '$lib/components/Header.svelte';
</script>

<svelte:head>
    <title>Staff Dashboard | The Hut Event Managing System</title>
    <meta name="description" content="Staff dashboard" />
</svelte:head>

<Header
    portalTitle="Community Centre Staff Portal"
    showLogout={true}
/>

<section class="dashboard-page">
    <div class="titles">
        <h1>Dashboard</h1>
        <p>Welcome back! Where do we start today?</p>
    </div>

    <div class="attendance">
        <h1>Tick Attendance</h1>
        <p>Record attendance for ongoing program.</p>
    </div>

    <div class="add-participant">
        <h1>Add Participant</h1>
        <p>Register new participants or assign them into a program.</p>
    </div>

    <div class="add-program">
        <h1>Add Program</h1>
        <p>Register information of new programs.</p>
    </div>

    <div class="record">
        <h1>Search Participant</h1>
        <p>Search activity records of participants.</p>
    </div>

    <div class="report">
        <h1>View Reports</h1>
        <p>Browse attendance and program statistics.</p>
    </div>

    <div class="training">
        <h1>Start training</h1>
        <p>Get to know how the system works.</p>
    </div>
</section>

<style>
    :global(body) {
        margin: 0;
        background: #f8fafc;
        font-family: Arial, Helvetica, sans-serif;
        color: #0f172a;
    }

    .dashboard-page {
        min-height: calc(100vh - 112px);
        background: #f8fafc;
        padding: 40px 64px 56px;
        box-sizing: border-box;

        display: grid;
        grid-template-columns: repeat(3, minmax(280px, 1fr));
        gap: 28px;
    }

    .titles {
        grid-column: 1 / -1;
        margin-bottom: 4px;
    }

    .titles h1 {
        margin: 0 0 10px;
        font-size: clamp(30px, 4vw, 40px);
        font-weight: 700;
        line-height: 1.1;
        color: #0f172a;
    }

    .titles p {
        margin: 0;
        font-size: 15px;
        line-height: 1.5;
        color: #475569;
    }

    /* 所有功能块共用同一套盒子样式 */
    .attendance,
    .add-participant,
    .add-program,
    .record,
    .report,
    .training {
        position: relative;
        min-height: 220px;
        padding: 112px 30px 30px;
        background: #ffffff;
        border: 2px solid #e5e7eb;
        border-radius: 22px;
        box-sizing: border-box;
        transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease;
    }

    .attendance:hover,
    .add-participant:hover,
    .add-program:hover,
    .record:hover,
    .report:hover,
    .training:hover {
        transform: translateY(-3px);
        box-shadow: 0 10px 24px rgba(15, 23, 42, 0.08);
        border-color: #cbd5e1;
    }

    .attendance h1,
    .add-participant h1,
    .add-program h1,
    .record h1,
    .report h1,
    .training h1 {
        margin: 0 0 12px;
        font-size: clamp(20px, 2vw, 25px);
        font-weight: 600;
        line-height: 1.2;
        color: #0f172a;
    }

    .attendance p,
    .add-participant p,
    .add-program p,
    .record p,
    .report p,
    .training p {
        margin: 0;
        font-size: 14px;
        line-height: 1.55;
        color: #475569;
    }

    /* 每个块左上角的小图标方块 */
    .attendance::before,
    .add-participant::before,
    .add-program::before,
    .record::before,
    .report::before,
    .training::before {
        position: absolute;
        top: 28px;
        left: 30px;
        width: 68px;
        height: 68px;
        border-radius: 14px;

        display: flex;
        align-items: center;
        justify-content: center;

        color: #ffffff;
        font-size: 30px;
        font-weight: 800;
        line-height: 1;
    }

    .attendance::before {
        content: '✓';
        background: #22c55e;
    }

    .add-participant::before {
        content: '+';
        background: #3b82f6;
    }

    .add-program::before {
        content: 'P';
        background: #a855f7;
    }

    .record::before {
        content: '⌕';
        background: #f97316;
    }

    .report::before {
        content: '▥';
        background: #14b8a6;
    }

    .training::before {
        content: 'i';
        background: #64748b;
    }

    @media (max-width: 1200px) {
        .dashboard-page {
            grid-template-columns: repeat(2, minmax(280px, 1fr));
            padding: 36px 32px 48px;
        }
    }

    @media (max-width: 760px) {
        .dashboard-page {
            grid-template-columns: 1fr;
            padding: 28px 16px 40px;
            gap: 20px;
        }

        .attendance,
        .add-participant,
        .add-program,
        .record,
        .report,
        .training {
            min-height: 190px;
            padding: 102px 24px 24px;
        }

        .attendance::before,
        .add-participant::before,
        .add-program::before,
        .record::before,
        .report::before,
        .training::before {
            top: 24px;
            left: 24px;
            width: 60px;
            height: 60px;
            font-size: 26px;
        }
    }
</style>