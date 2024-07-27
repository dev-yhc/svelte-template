<script>
	let recommendations = [
	  {
		title: "토스 서류패스 이벤트",
		description: "Product Designer (Tools)",
		image: "https://via.placeholder.com/300x150",
		tags: []
	  },
	  {
		title: "프론트엔드 테스트 자동화 전략",
		description: "2. 요구사항 분석",
		author: "유덕남 | 2024.07.21",
		tags: ["웹 개발", "Frontend", "Testing"]
	  }
	];
  
	let jobPostings = [
	  {
		title: "[MAI] Backend Engineer",
		company: "달파",
		image: "https://via.placeholder.com/300x150"
	  },
	  {
		title: "토스 서류패스 이벤트",
		company: "Product Designer (Tools)",
		image: "https://via.placeholder.com/300x150"
	  },
	  {
		title: "DevOps Engineer",
		company: "핏펫",
		image: "https://via.placeholder.com/300x150"
	  },
	  {
		title: "Front-End Developer",
		company: "테스트뱅크",
		image: "https://via.placeholder.com/300x150"
	  }
	];
  
	let categories = [
	  "일반 개발", "웹 개발", "Javascript", "React", "Python", 
	  "Infra Structure", "Database", "빅데이터 · AI · 머신러닝", 
	  "일반 기획", "서비스 기획", "프로덕트 관리"
	];
  </script>
  
  <style>
	:global(body) {
	  font-family: Arial, sans-serif;
	  background-color: #1c1c1e;
	  color: #ffffff;
	  margin: 0;
	  padding: 0;
	}
	.container {
	  display: flex;
	  padding: 20px;
	}
	.sidebar {
	  width: 200px;
	  margin-right: 20px;
	}
	.sidebar h2 {
	  color: #ff9500;
	}
	.sidebar ul {
	  list-style-type: none;
	  padding: 0;
	}
	.sidebar ul li {
	  margin: 10px 0;
	  color: #9e9e9e;
	}
	.content {
	  flex-grow: 1;
	}
	.grid-container {
	  display: grid;
	  grid-template-columns: repeat(3, 1fr);
	  gap: 20px;
	}
	.recommendation, .job-postings {
	  margin-bottom: 20px;
	}
	.card {
	  background-color: #2c2c2e;
	  border-radius: 10px;
	  padding: 15px;
	}
	.card img {
	  width: 100%;
	  border-radius: 10px;
	}
	.card h3, .card p {
	  margin: 10px 0;
	}
	.tags {
	  display: flex;
	  flex-wrap: wrap;
	}
	.tag {
	  background-color: #323233;
	  border-radius: 5px;
	  padding: 5px 10px;
	  margin-right: 5px;
	  color: #7fa8ff;
	}
  </style>
  
  <div class="container">
	<div class="sidebar">
	  <h2>관심 카테고리</h2>
	  <ul>
		{#each categories as category}
		  <li>{category}</li>
		{/each}
	  </ul>
	</div>
	<div class="content">
	  <div class="recommendation">
		<h2>양현철님께 추천해요!</h2>
		<div class="grid-container">
		  {#each recommendations as recommendation}
			<div class="card">
			  <h3>{recommendation.title}</h3>
			  <p>{recommendation.description}</p>
			  {#if recommendation.image}
				<img src={recommendation.image} alt={recommendation.title} />
			  {/if}
			  {#if recommendation.author}
				<p>{recommendation.author}</p>
			  {/if}
			  {#if recommendation.tags.length}
				<div class="tags">
				  {#each recommendation.tags as tag}
					<div class="tag">{tag}</div>
				  {/each}
				</div>
			  {/if}
			</div>
		  {/each}
		</div>
	  </div>
	  <div class="job-postings">
		<h2>개발 채용 공고</h2>
		<div class="grid-container">
		  {#each jobPostings as job}
			<div class="card">
			  <img src={job.image} alt={job.title} />
			  <h3>{job.title}</h3>
			  <p>{job.company}</p>
			</div>
		  {/each}
		</div>
	  </div>
	</div>
  </div>
  