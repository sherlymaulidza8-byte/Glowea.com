<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Simple Dashboard</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      background: #f4f6f9;
      overflow-x: hidden;
    }

    .sidebar {
      width: 250px;
      min-height: 100vh;
      background: #1f2937;
      color: #fff;
      position: fixed;
      top: 0;
      left: 0;
      padding: 20px;
    }

    .sidebar h4 {
      margin-bottom: 30px;
      font-weight: 700;
    }

    .sidebar a {
      color: #d1d5db;
      text-decoration: none;
      display: block;
      padding: 10px 12px;
      border-radius: 8px;
      margin-bottom: 8px;
    }

    .sidebar a:hover {
      background: #374151;
      color: #fff;
    }

    .main-content {
      margin-left: 250px;
      padding: 20px;
    }

    .card-stat {
      border: none;
      border-radius: 16px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.06);
    }

    .topbar {
      background: #fff;
      padding: 15px 20px;
      border-radius: 16px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.06);
      margin-bottom: 20px;
    }

    @media (max-width: 768px) {
      .sidebar {
        position: relative;
        width: 100%;
        min-height: auto;
      }
      .main-content {
        margin-left: 0;
      }
    }
  </style>
</head>
<body>

  <div class="sidebar">
    <h4>My Dashboard</h4>
    <a href="#"><i class="fa-solid fa-gauge me-2"></i>Dashboard</a>
    <a href="#"><i class="fa-solid fa-users me-2"></i>Users</a>
    <a href="#"><i class="fa-solid fa-chart-line me-2"></i>Reports</a>
    <a href="#"><i class="fa-solid fa-gear me-2"></i>Settings</a>
    <a href="#"><i class="fa-solid fa-right-from-bracket me-2"></i>Logout</a>
  </div>

  <div class="main-content">
    <div class="topbar d-flex justify-content-between align-items-center">
      <h3 class="mb-0">Dashboard</h3>
      <div>
        <span class="me-2">Welcome, Ilham</span>
        <i class="fa-solid fa-user-circle fa-lg"></i>
      </div>
    </div>

    <div class="row g-3 mb-4">
      <div class="col-md-4">
        <div class="card card-stat p-3">
          <h6>Total Users</h6>
          <h3>1,250</h3>
          <small class="text-success">+12% from last month</small>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card card-stat p-3">
          <h6>Revenue</h6>
          <h3>$8,430</h3>
          <small class="text-success">+8% from last month</small>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card card-stat p-3">
          <h6>Orders</h6>
          <h3>320</h3>
          <small class="text-danger">-2% from last month</small>
        </div>
      </div>
    </div>

    <div class="row g-3">
      <div class="col-md-8">
        <div class="card card-stat p-3">
          <h5>Sales Overview</h5>
          <canvas id="salesChart" height="120"></canvas>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card card-stat p-3">
          <h5>Recent Activity</h5>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">New user registered</li>
            <li class="list-group-item">Order #1234 completed</li>
            <li class="list-group-item">Server backup done</li>
            <li class="list-group-item">New report uploaded</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="card card-stat p-3 mt-4">
      <h5>Latest Data</h5>
      <div class="table-responsive">
        <table class="table align-middle">
          <thead>
            <tr>
              <th>ID</th>
              <th>Name</th>
              <th>Status</th>
              <th>Date</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>#001</td>
              <td>Project Alpha</td>
              <td><span class="badge bg-success">Done</span></td>
              <td>2026-06-04</td>
            </tr>
            <tr>
              <td>#002</td>
              <td>Project Beta</td>
              <td><span class="badge bg-warning text-dark">Pending</span></td>
              <td>2026-06-03</td>
            </tr>
            <tr>
              <td>#003</td>
              <td>Project Gamma</td>
              <td><span class="badge bg-danger">Failed</span></td>
              <td>2026-06-02</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>

  <script>
    const ctx = document.getElementById('salesChart').getContext('2d');
    new Chart(ctx, {
      type: 'line',
      data: {
        labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
        datasets: [{
          label: 'Sales',
          data: [12, 19, 15, 25, 22, 30],
          borderColor: '#2563eb',
          backgroundColor: 'rgba(37, 99, 235, 0.1)',
          tension: 0.4,
          fill: true
        }]
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            display: true
          }
        }
      }
    });
  </script>

</body>
</html>
