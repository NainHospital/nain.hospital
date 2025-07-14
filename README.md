<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>บันทึกการสำรวจลูกน้ำยุงลาย</title>
  <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
  <style>
    * {
      box-sizing: border-box;
    }
    
    body {
      font-family: "Sarabun", "Noto Sans Thai", Arial, sans-serif;
      background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
      margin: 0;
      padding: 10px;
      font-size: 16px;
      line-height: 1.4;
    }
    
    .container {
      max-width: 100%;
      margin: 0 auto;
      background: #fff;
      border-radius: 15px;
      box-shadow: 0 8px 32px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    
    .header {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      padding: 20px;
      text-align: center;
    }
    
    .header h1 {
      margin: 0;
      font-size: 20px;
      font-weight: 600;
      text-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }
    
    .header p {
      margin: 8px 0 0 0;
      font-size: 14px;
      opacity: 0.9;
    }
    
    .form-content {
      padding: 20px;
    }
    
    .house-section {
      background: #f8f9ff;
      border: 2px solid #e1e8ff;
      border-radius: 12px;
      padding: 16px;
      margin-bottom: 20px;
    }
    
    .house-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 16px;
      padding-bottom: 12px;
      border-bottom: 2px solid #ddd;
    }
    
    .house-number {
      background: #667eea;
      color: white;
      width: 35px;
      height: 35px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 16px;
    }
    
    .house-input-container {
      flex: 1;
      margin-left: 12px;
    }
    
    .house-input-container label {
      display: block;
      font-weight: 600;
      color: #333;
      margin-bottom: 4px;
      font-size: 14px;
    }
    
    .house-input {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border: 2px solid #ddd;
      border-radius: 8px;
      background: white;
    }
    
    .house-input:focus {
      outline: none;
      border-color: #667eea;
      box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
    }
    
    .delete-btn {
      background: #ff4757;
      color: white;
      border: none;
      width: 35px;
      height: 35px;
      border-radius: 50%;
      cursor: pointer;
      font-size: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.2s;
    }
    
    .delete-btn:hover {
      background: #ff3838;
      transform: scale(1.05);
    }
    
    .categories {
      display: grid;
      gap: 16px;
    }
    
    .category-group {
      background: white;
      border-radius: 10px;
      border: 1px solid #e0e6ed;
      overflow: hidden;
    }
    
    .category-header {
      background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
      color: white;
      padding: 12px 16px;
      font-weight: 600;
      font-size: 15px;
    }
    
    .category-content {
      padding: 16px;
    }
    
    .location-group {
      margin-bottom: 16px;
    }
    
    .location-title {
      font-weight: 600;
      color: #2d3436;
      margin-bottom: 8px;
      font-size: 14px;
      display: flex;
      align-items: center;
    }
    
    .location-icon {
      width: 20px;
      height: 20px;
      margin-right: 8px;
      background: #74b9ff;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 12px;
    }
    
    .input-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-bottom: 8px;
    }
    
    .input-group {
      background: #f8f9fa;
      border-radius: 8px;
      padding: 12px;
      border: 1px solid #e9ecef;
    }
    
    .input-group label {
      display: block;
      font-size: 12px;
      color: #6c757d;
      margin-bottom: 4px;
      font-weight: 500;
    }
    
    .number-input {
      width: 100%;
      padding: 10px;
      font-size: 18px;
      border: 2px solid #dee2e6;
      border-radius: 6px;
      text-align: center;
      background: white;
      font-weight: 600;
    }
    
    .number-input:focus {
      outline: none;
      border-color: #74b9ff;
      box-shadow: 0 0 0 3px rgba(116, 185, 255, 0.1);
    }
    
    .survey-input {
      border-color: #00b894;
    }
    
    .survey-input:focus {
      border-color: #00a085;
      box-shadow: 0 0 0 3px rgba(0, 184, 148, 0.1);
    }
    
    .found-input {
      border-color: #e17055;
    }
    
    .found-input:focus {
      border-color: #d63031;
      box-shadow: 0 0 0 3px rgba(225, 112, 85, 0.1);
    }
    
    .summary-section {
      background: linear-gradient(135deg, #ffeaa7 0%, #fab1a0 100%);
      border-radius: 10px;
      padding: 16px;
      margin-top: 16px;
    }
    
    .summary-title {
      font-weight: 600;
      color: #2d3436;
      margin-bottom: 12px;
      font-size: 15px;
      text-align: center;
    }
    
    .summary-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }
    
    .summary-item {
      background: rgba(255,255,255,0.8);
      border-radius: 8px;
      padding: 12px;
      text-align: center;
    }
    
    .summary-item label {
      display: block;
      font-size: 12px;
      color: #636e72;
      margin-bottom: 4px;
      font-weight: 500;
    }
    
    .summary-input {
      width: 100%;
      padding: 10px;
      font-size: 20px;
      font-weight: bold;
      text-align: center;
      border: 2px solid #fdcb6e;
      border-radius: 6px;
      background: white;
      color: #2d3436;
    }
    
    .summary-input:focus {
      outline: none;
      border-color: #e17055;
      box-shadow: 0 0 0 3px rgba(225, 112, 85, 0.1);
    }
    
    .button-container {
      padding: 20px;
      background: #f8f9fa;
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }
    
    .btn {
      flex: 1;
      min-height: 50px;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }
    
    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }
    
    .btn-add {
      background: linear-gradient(135deg, #00b894 0%, #00a085 100%);
      color: white;
    }
    
    .btn-submit {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
    }
    
    .btn-reset {
      background: linear-gradient(135deg, #fd79a8 0%, #e84393 100%);
      color: white;
    }
    
    .loading {
      display: none;
      text-align: center;
      padding: 20px;
      color: #667eea;
    }
    
    .success-message {
      display: none;
      background: #d4edda;
      color: #155724;
      padding: 15px;
      border-radius: 8px;
      margin: 20px;
      text-align: center;
      border: 1px solid #c3e6cb;
    }
    
    .error-message {
      display: none;
      background: #f8d7da;
      color: #721c24;
      padding: 15px;
      border-radius: 8px;
      margin: 20px;
      text-align: center;
      border: 1px solid #f5c6cb;
    }
    
    .surveyor-info {
      background: linear-gradient(135deg, #e8f5e8 0%, #d4edda 100%);
      padding: 20px;
      border-bottom: 3px solid #28a745;
    }
    
    .info-grid {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 16px;
      max-width: 800px;
      margin: 0 auto;
    }
    
    .info-group {
      display: flex;
      flex-direction: column;
    }
    
    .info-group label {
      font-weight: 600;
      color: #2d5016;
      margin-bottom: 6px;
      font-size: 14px;
    }
    
    .info-group select,
    .info-group input[type="text"] {
      padding: 12px;
      font-size: 16px;
      border: 2px solid #28a745;
      border-radius: 8px;
      background: white;
      color: #2d5016;
      font-weight: 500;
    }
    
    .info-group select:focus,
    .info-group input[type="text"]:focus {
      outline: none;
      border-color: #20c997;
      box-shadow: 0 0 0 3px rgba(40, 167, 69, 0.1);
    }
    
    .info-group input[type="date"] {
      padding: 12px;
      font-size: 16px;
      border: 2px solid #6c757d;
      border-radius: 8px;
      background: #f8f9fa;
      color: #495057;
      font-weight: 500;
    }
    
    .address-text {
      padding: 12px;
      background: rgba(255,255,255,0.8);
      border: 2px solid #6c757d;
      border-radius: 8px;
      color: #495057;
      font-weight: 500;
      font-size: 14px;
      text-align: center;
    }
    
    .ci-circle-container {
      position: relative;
      width: 60px;
      height: 60px;
      margin: 0 auto;
    }
    .ci-circle {
      display: block;
      transform: rotate(-90deg);
    }
    .ci-text {
      position: absolute;
      top: 0; left: 0; width: 60px; height: 60px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 1.1em;
      color: #00b894;
      pointer-events: none;
    }
    
    /* Highlight required fields if empty */
    .required-highlight {
      border-color: #ff3b30 !important;
      background: #fff6f6 !important;
      box-shadow: 0 0 0 2px #ffb3b3 !important;
    }
    .required-label {
      color: #ff3b30 !important;
      font-weight: bold;
    }
    .required-asterisk {
      color: #ff3b30;
    }
    
    @media (max-width: 768px) {
      body {
        padding: 5px;
        font-size: 16px;
      }
      
      .header h1 {
        font-size: 18px;
      }
      
      .form-content {
        padding: 15px;
      }
      
      .number-input {
        font-size: 16px;
        padding: 12px;
      }
      
      .btn {
        min-height: 45px;
        font-size: 15px;
      }
      
      .info-grid {
        grid-template-columns: 1fr;
        gap: 12px;
      }
      
      .surveyor-info {
        padding: 15px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>📋 บันทึกการสำรวจลูกน้ำยุงลาย</h1>
      <p>รพ.สต.นาอิน</p>
    </div>
    
    <form id="surveyForm">
      <div class="surveyor-info">
        <div class="info-grid">
          <div class="info-group">
            <label for="village" id="label-village">หมู่ที่ <span class="required-asterisk">*</span></label>
            <select id="village" name="village" required>
              <option value="">เลือกหมู่</option>
              <option value="1">หมู่ 1</option>
              <option value="2">หมู่ 2</option>
              <option value="3">หมู่ 3</option>
              <option value="4">หมู่ 4</option>
              <option value="5">หมู่ 5</option>
              <option value="6">หมู่ 6</option>
              <option value="7">หมู่ 7</option>
            </select>
          </div>
          
          <div class="info-group">
            <label>ที่อยู่</label>
            <div class="address-text">ตำบลนาอิน อำเภอพิชัย จังหวัดอุตรดิตถ์</div>
          </div>
          
          <div class="info-group">
            <label for="surveyor" id="label-surveyor">ผู้สำรวจ <span class="required-asterisk">*</span></label>
            <select id="surveyor" name="surveyor" required>
              <option value="">เลือกผู้สำรวจ</option>
              <!-- รายชื่อจะถูกเติมโดย JS -->
            </select>
          </div>
          
          <div class="info-group">
            <label for="surveyDate">วันที่สำรวจ</label>
            <input type="date" id="surveyDate" name="surveyDate" readonly>
          </div>
        </div>
      </div>
      
      <div class="success-message" id="successMessage">
        ✅ ส่งข้อมูลเรียบร้อยแล้ว ขอบคุณครับ!
      </div>
      
      <div class="error-message" id="errorMessage">
        ❌ เกิดข้อผิดพลาด กรุณาลองใหม่อีกครั้ง
      </div>
      
      <div class="loading" id="loading">
        ⏳ กำลังส่งข้อมูล...
      </div>
      
      <div class="form-content" id="formContent">
        <!-- แถวข้อมูลจะถูกเพิ่มที่นี่ -->
      </div>
      
      <div class="button-container">
        <button type="button" class="btn btn-add" id="addRowBtn">
          ➕ เพิ่มบ้าน
        </button>
        <button type="button" class="btn btn-reset" id="resetBtn">
          🔄 ล้างข้อมูล
        </button>
        <button type="submit" class="btn btn-submit">
          📤 ส่งข้อมูล
        </button>
      </div>
    </form>
  </div>

  <script>
    const scriptURL = 'https://script.google.com/macros/s/AKfycbxs-_ehAAZudE6eaQYRz2a91nPC5bZ1lG1y8iWZU16e3xSZ-2Nmsv8TCUpr8G5IKAIHiA/exec';
    const formContent = document.getElementById('formContent');
    const addRowBtn = document.getElementById('addRowBtn');
    const resetBtn = document.getElementById('resetBtn');
    const loading = document.getElementById('loading');
    const successMessage = document.getElementById('successMessage');
    const errorMessage = document.getElementById('errorMessage');
    
    let rowCounter = 0;
    
    const categories = [
      { key: 'use', name: 'น้ำใช้', icon: '🚿' },
      { key: 'drink', name: 'น้ำดื่ม', icon: '🥤' },
      { key: 'toilet', name: 'ห้องน้ำ', icon: '🚽' },
      { key: 'flower', name: 'แจกัน/กระถาง', icon: '🌺' },
      { key: 'other', name: 'อื่นๆ', icon: '📦' }
    ];
    
    function createHouseSection(houseNum) {
      const section = document.createElement('div');
      section.className = 'house-section';
      section.dataset.houseNum = houseNum;

      section.innerHTML = `
        <div class="house-header">
          <div class="house-number">${houseNum}</div>
          <div class="house-input-container">
            <label for="houseNo_${houseNum}" id="label-houseNo_${houseNum}">บ้านเลขที่ <span class="required-asterisk">*</span></label>
            <div style="display: flex; align-items: center; gap: 4px;">
              <input type="number"
                     class="house-input house-no-main"
                     id="houseNo_main_${houseNum}"
                     name="houseNo_main_${houseNum}"
                     placeholder="เลขที่"
                     min="0"
                     inputmode="numeric"
                     pattern="[0-9]*"
                     style="width: 60px; text-align: right;">
              <label style="font-size: 1.2em; padding: 0 2px;">/</label>
              <input type="number"
                     class="house-input house-no-sub"
                     id="houseNo_sub_${houseNum}"
                     name="houseNo_sub_${houseNum}"
                     placeholder="เลขย่อย"
                     min="0"
                     inputmode="numeric"
                     pattern="[0-9]*"
                     style="width: 50px; text-align: left;">
            </div>
          </div>
          ${houseNum > 1 ? `<button type="button" class="delete-btn" onclick="deleteHouse(${houseNum})" title="ลบบ้านนี้">×</button>` : ''}
        </div>
        
        <div class="categories">
          <div class="category-group">
            <div class="category-header">🏠 ในอาคาร</div>
            <div class="category-content">
              ${categories.map(cat => cat.key === 'other' ? `
                <div class="location-group">
                  <div class="input-group" style="margin-bottom:8px;">
                    <label>รายละเอียดอื่นๆ</label>
                    <input type="text" 
                           class="number-input in-other-detail"
                           name="in_other_detail_${houseNum}"
                           placeholder="ระบุรายละเอียด"
                           data-other-detail="in_${houseNum}">
                  </div>
                  <div class="location-title">
                    <span class="location-icon">${cat.icon}</span>
                    ${cat.name}
                  </div>
                  <div class="input-row">
                    <div class="input-group">
                      <label for="in_${cat.key}_survey_${houseNum}">สำรวจ (จำนวน)</label>
                      <input type="number" 
                             class="number-input survey-input in-other-amount"
                             name="in_${cat.key}_survey_${houseNum}"
                             id="in_${cat.key}_survey_${houseNum}"
                             min="0" 
                             value="0"
                             data-other-amount="in_${houseNum}"
                             placeholder="0"
                             title="กรอกจำนวนสำรวจในอาคาร - อื่นๆ"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                    <div class="input-group">
                      <label for="in_${cat.key}_found_${houseNum}">พบลูกน้ำ (จำนวน)</label>
                      <input type="number" 
                             class="number-input found-input in-other-amount"
                             name="in_${cat.key}_found_${houseNum}"
                             id="in_${cat.key}_found_${houseNum}"
                             min="0" 
                             value="0"
                             data-other-amount="in_${houseNum}"
                             placeholder="0"
                             title="กรอกจำนวนพบลูกน้ำในอาคาร - อื่นๆ"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                  </div>
                  <div class="in-other-warning" style="color:#ff3b30; font-size:13px; display:none; margin-top:4px;"></div>
                </div>
              ` : `
                <div class="location-group">
                  <div class="location-title">
                    <span class="location-icon">${cat.icon}</span>
                    ${cat.name}
                  </div>
                  <div class="input-row">
                    <div class="input-group">
                      <label for="in_${cat.key}_survey_${houseNum}">สำรวจ (จำนวน)</label>
                      <input type="number" 
                             class="number-input survey-input" 
                             name="in_${cat.key}_survey_${houseNum}"
                             id="in_${cat.key}_survey_${houseNum}"
                             min="0" 
                             value="0"
                             placeholder="0"
                             title="กรอกจำนวนสำรวจในอาคาร - ${cat.name}"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                    <div class="input-group">
                      <label for="in_${cat.key}_found_${houseNum}">พบลูกน้ำ (จำนวน)</label>
                      <input type="number" 
                             class="number-input found-input" 
                             name="in_${cat.key}_found_${houseNum}"
                             id="in_${cat.key}_found_${houseNum}"
                             min="0" 
                             value="0"
                             placeholder="0"
                             title="กรอกจำนวนพบลูกน้ำในอาคาร - ${cat.name}"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                  </div>
                </div>
              `).join('')}
            </div>
          </div>
          
          <div class="category-group">
            <div class="category-header">🌳 นอกอาคาร</div>
            <div class="category-content">
              ${categories.map(cat => cat.key === 'other' ? `
                <div class="location-group">
                  <div class="input-group" style="margin-bottom:8px;">
                    <label>รายละเอียดอื่นๆ</label>
                    <input type="text" 
                           class="number-input out-other-detail"
                           name="out_other_detail_${houseNum}"
                           placeholder="ระบุรายละเอียด"
                           data-other-detail="out_${houseNum}">
                  </div>
                  <div class="location-title">
                    <span class="location-icon">${cat.icon}</span>
                    ${cat.name}
                  </div>
                  <div class="input-row">
                    <div class="input-group">
                      <label for="out_${cat.key}_survey_${houseNum}">สำรวจ (จำนวน)</label>
                      <input type="number" 
                             class="number-input survey-input out-other-amount"
                             name="out_${cat.key}_survey_${houseNum}"
                             id="out_${cat.key}_survey_${houseNum}"
                             min="0" 
                             value="0"
                             data-other-amount="out_${houseNum}"
                             placeholder="0"
                             title="กรอกจำนวนสำรวจนอกอาคาร - อื่นๆ"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                    <div class="input-group">
                      <label for="out_${cat.key}_found_${houseNum}">พบลูกน้ำ (จำนวน)</label>
                      <input type="number" 
                             class="number-input found-input out-other-amount"
                             name="out_${cat.key}_found_${houseNum}"
                             id="out_${cat.key}_found_${houseNum}"
                             min="0" 
                             value="0"
                             data-other-amount="out_${houseNum}"
                             placeholder="0"
                             title="กรอกจำนวนพบลูกน้ำนอกอาคาร - อื่นๆ"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                  </div>
                  <div class="out-other-warning" style="color:#ff3b30; font-size:13px; display:none; margin-top:4px;"></div>
                </div>
              ` : `
                <div class="location-group">
                  <div class="location-title">
                    <span class="location-icon">${cat.icon}</span>
                    ${cat.name}
                  </div>
                  <div class="input-row">
                    <div class="input-group">
                      <label for="out_${cat.key}_survey_${houseNum}">สำรวจ (จำนวน)</label>
                      <input type="number" 
                             class="number-input survey-input" 
                             name="out_${cat.key}_survey_${houseNum}"
                             id="out_${cat.key}_survey_${houseNum}"
                             min="0" 
                             value="0"
                             placeholder="0"
                             title="กรอกจำนวนสำรวจนอกอาคาร - ${cat.name}"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                    <div class="input-group">
                      <label for="out_${cat.key}_found_${houseNum}">พบลูกน้ำ (จำนวน)</label>
                      <input type="number" 
                             class="number-input found-input" 
                             name="out_${cat.key}_found_${houseNum}"
                             id="out_${cat.key}_found_${houseNum}"
                             min="0" 
                             value="0"
                             placeholder="0"
                             title="กรอกจำนวนพบลูกน้ำนอกอาคาร - ${cat.name}"
                             onchange="calculateSummary(${houseNum})">
                    </div>
                  </div>
                </div>
              `).join('')}
            </div>
          </div>
        </div>
        
        <div class="summary-section">
          <div class="summary-title">📊 สรุปรวม</div>
          <div class="summary-row">
            <div class="summary-item">
              <label for="sum_survey_${houseNum}">รวมสำรวจทั้งหมด</label>
              <input type="number" 
                     class="summary-input" 
                     name="sum_survey_${houseNum}"
                     id="sum_survey_${houseNum}"
                     readonly
                     placeholder="0"
                     title="รวมจำนวนสำรวจทั้งหมด">
            </div>
            <div class="summary-item">
              <label for="sum_found_${houseNum}">รวมพบลูกน้ำ</label>
              <input type="number" 
                     class="summary-input" 
                     name="sum_found_${houseNum}"
                     id="sum_found_${houseNum}"
                     readonly
                     placeholder="0"
                     title="รวมจำนวนพบลูกน้ำทั้งหมด">
            </div>
            <div class="summary-item" style="height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; width: 100%; grid-column: span 2;">
              <label>CI (%)</label>
              <div class="ci-circle-container">
                <svg class="ci-circle" width="60" height="60">
                  <circle cx="30" cy="30" r="26" stroke="#eee" stroke-width="6" fill="none"/>
                  <circle cx="30" cy="30" r="26" stroke="#00b894" stroke-width="6" fill="none"
                    stroke-dasharray="163.36" stroke-dashoffset="163.36"
                    data-ci-arc
                  />
                </svg>
                <div class="ci-text" data-ci-text>0%</div>
              </div>
              <div class="ci-label" data-ci-label style="margin-top:6px;font-size:0.95em; font-weight:bold; text-shadow: 0 1px 2px #fff, 0 0 2px #fff;"></div>
              <input type="hidden" name="ci_${houseNum}">
            </div>
          </div>
        </div>
      `;
      
      return section;
    }
    
    function addHouse() {
      rowCounter++;
      const houseSection = createHouseSection(rowCounter);
      formContent.appendChild(houseSection);

      // ตั้งค่า event เฉพาะ number input (survey/found)
      setTimeout(() => {
        // เลื่อนไปยังบ้านที่เพิ่มใหม่
        houseSection.scrollIntoView({ behavior: 'smooth', block: 'start' });
        // โฟกัสที่ช่องบ้านเลขที่
        houseSection.querySelector('.house-input').focus();

        // จัดการ default/restore 0 สำหรับ number input
        houseSection.querySelectorAll('input.number-input[type="number"]').forEach(input => {
          // ถ้าไม่มีค่า ให้ใส่ 0
          if (!input.value || input.value === '') input.value = '0';

          // Focus: ถ้าเป็น 0 ให้ลบออก
          input.addEventListener('focus', function() {
            if (this.value === '0') this.value = '';
          });
          // Input: ถ้าลบจนว่าง ให้ใส่ 0
          input.addEventListener('input', function() {
            // ถ้าเป็นค่าว่าง ให้ใส่ 0 (แต่ต้อง delay เพื่อไม่รบกวนการพิมพ์)
            if (this.value === '') {
              setTimeout(() => {
                if (this.value === '') this.value = '0';
              }, 100);
            }
            // ถ้าพิมพ์เลข 0 ตัวเดียว ให้เหลือ 0 เดียว ไม่ต้องซ้อน 00
            if (/^0\d+/.test(this.value)) {
              this.value = this.value.replace(/^0+/, '');
              if (this.value === '') this.value = '0';
            }
          });
          // Blur: ถ้าค่าว่าง ให้ใส่ 0
          input.addEventListener('blur', function() {
            if (this.value === '') this.value = '0';
          });
        });
      }, 100);
    }
    // สำหรับบ้านที่ถูกสร้างไว้แล้ว (บ้านแรก)
    document.addEventListener('DOMContentLoaded', function() {
      setTimeout(() => {
        document.querySelectorAll('input.number-input[type="number"]').forEach(input => {
          if (!input.value || input.value === '') input.value = '0';
          input.addEventListener('focus', function() {
            if (this.value === '0') this.value = '';
          });
          input.addEventListener('input', function() {
            if (this.value === '') {
              setTimeout(() => {
                if (this.value === '') this.value = '0';
              }, 100);
            }
            if (/^0\d+/.test(this.value)) {
              this.value = this.value.replace(/^0+/, '');
              if (this.value === '') this.value = '0';
            }
          });
          input.addEventListener('blur', function() {
            if (this.value === '') this.value = '0';
          });
        });
      }, 300);
    });
    
    function deleteHouse(houseNum) {
      if (confirm('ต้องการลบข้อมูลบ้านนี้หรือไม่?')) {
        const section = document.querySelector(`[data-house-num="${houseNum}"]`);
        if (section) {
          section.remove();
        }
      }
    }
    
    function calculateSummary(houseNum) {
      // รวมเฉพาะ input ที่เกี่ยวข้องกับ "สำรวจ" สำหรับ "รวมสำรวจทั้งหมด"
      let totalSurvey = 0;
      // รวมเฉพาะ input ที่เกี่ยวข้องกับ "พบลูกน้ำ" สำหรับ "รวมพบลูกน้ำ"
      let totalFound = 0;

      const section = document.querySelector(`[data-house-num="${houseNum}"]`);
      if (section) {
        // เฉพาะ input ที่เป็นช่องกรอก (ไม่รวม summary)
        const surveyInputs = section.querySelectorAll(
          `input.number-input.survey-input[name^="in_"][name$="_survey_${houseNum}"],input.number-input.survey-input[name^="out_"][name$="_survey_${houseNum}"]`
        );
        const foundInputs = section.querySelectorAll(
          `input.number-input.found-input[name^="in_"][name$="_found_${houseNum}"],input.number-input.found-input[name^="out_"][name$="_found_${houseNum}"]`
        );

        surveyInputs.forEach(input => {
          totalSurvey += parseInt(input.value) || 0;
        });

        foundInputs.forEach(input => {
          totalFound += parseInt(input.value) || 0;
        });

        // อัพเดทค่าสรุป
        const summaryTotalSurvey = section.querySelector(`input[name="sum_survey_${houseNum}"]`);
        const summaryTotalFound = section.querySelector(`input[name="sum_found_${houseNum}"]`);
        const summaryCI = section.querySelector(`input[name="ci_${houseNum}"]`);
        const ciArc = section.querySelector('[data-ci-arc]');
        const ciText = section.querySelector('[data-ci-text]');
        const ciLabelDiv = section.querySelector('[data-ci-label]');

        if (summaryTotalSurvey) summaryTotalSurvey.value = totalSurvey;
        if (summaryTotalFound) summaryTotalFound.value = totalFound;

        // คำนวณค่า CI
        let ciValue = 0;
        if (totalSurvey > 0) {
          ciValue = (totalFound / totalSurvey) * 100;
        }
        if (summaryCI) summaryCI.value = ciValue.toFixed(2);

        // สรุปข้อความและสี
        let ciLabel = '';
        let ciColor = '#00b894'; // เขียว
        if (ciValue === 0) {
          ciLabel = 'ปลอดภัย';
          ciColor = '#00b894'; // เขียว
        } else if (ciValue > 0 && ciValue <= 10) {
          ciLabel = 'ยอมรับได้ เสี่ยงต่ำ';
          ciColor = '#ffd600'; // เหลือง
        } else if (ciValue > 10) {
          ciLabel = 'เสี่ยงสูงต่อการระบาดของโรคไข้เลือดออก';
          ciColor = '#ff3b30'; // แดง
        }

        // วาดกราฟวงกลม
        if (ciArc) {
          const circleLen = 2 * Math.PI * 26; // r=26
          const percent = Math.max(0, Math.min(100, ciValue));
          ciArc.setAttribute('stroke-dasharray', circleLen);
          ciArc.setAttribute('stroke-dashoffset', circleLen - (circleLen * percent / 100));
          ciArc.setAttribute('stroke', ciColor);
        }

        // แสดงค่าในวงกลม
        if (ciText) {
          let percentText = totalSurvey > 0 ? ciValue.toFixed(1) + '%' : '0%';
          ciText.textContent = percentText;
          ciText.style.color = ciColor;
        }

        // แสดงข้อความสรุปด้านล่างวงกลม
        if (ciLabelDiv) {
          ciLabelDiv.textContent = ciLabel;
          ciLabelDiv.style.color = ciColor;
          ciLabelDiv.style.background = "#fff";
          ciLabelDiv.style.borderRadius = "6px";
          ciLabelDiv.style.padding = "2px 4px";
          ciLabelDiv.style.display = "inline-block";
          ciLabelDiv.style.boxShadow = "0 1px 4px rgba(0,0,0,0.08)";
        }
      }
    }
    
    function resetForm() {
      if (confirm('ต้องการล้างข้อมูลทั้งหมดหรือไม่?')) {
        formContent.innerHTML = '';
        rowCounter = 0;
        hideMessages();
        addHouse(); // เพิ่มบ้านแรก
      }
    }
    
    function hideMessages() {
      successMessage.style.display = 'none';
      errorMessage.style.display = 'none';
      loading.style.display = 'none';
    }
    
    // Utility to highlight required fields if empty
    function highlightRequiredFields() {
      // หมู่ที่
      const village = document.getElementById('village');
      const labelVillage = document.getElementById('label-village');
      if (!village.value) {
        village.classList.add('required-highlight');
        labelVillage.classList.add('required-label');
      } else {
        village.classList.remove('required-highlight');
        labelVillage.classList.remove('required-label');
      }

      // ผู้สำรวจ
      const surveyor = document.getElementById('surveyor');
      const labelSurveyor = document.getElementById('label-surveyor');
      if (!surveyor.value) {
        surveyor.classList.add('required-highlight');
        labelSurveyor.classList.add('required-label');
      } else {
        surveyor.classList.remove('required-highlight');
        labelSurveyor.classList.remove('required-label');
      }

      // บ้านเลขที่ (ทุกบ้าน)
      document.querySelectorAll('.house-section').forEach(section => {
        const input = section.querySelector('.house-input');
        const label = section.querySelector('label[for="' + input.id + '"]');
        if (input && label) {
          if (!input.value.trim()) {
            input.classList.add('required-highlight');
            label.classList.add('required-label');
          } else {
            input.classList.remove('required-highlight');
            label.classList.remove('required-label');
          }
        }
      });
    }

    // Event Listeners
    addRowBtn.addEventListener('click', () => {
      addHouse();
      setTimeout(highlightRequiredFields, 100);
    });
    resetBtn.addEventListener('click', resetForm);

    document.getElementById('village').addEventListener('change', function() {
      const village = this.value;
      const surveyorSelect = document.getElementById('surveyor');
      surveyorSelect.innerHTML = '<option value="">เลือกผู้สำรวจ</option>';
      if (surveyorsByVillage[village]) {
        surveyorsByVillage[village].forEach(person => {
          const opt = document.createElement('option');
          opt.value = person.value;
          opt.textContent = person.label;
          surveyorSelect.appendChild(opt);
        });
      }
      highlightRequiredFields();
    });
    document.getElementById('surveyor').addEventListener('change', highlightRequiredFields);

    // Delegate input event for house number fields
    document.addEventListener('input', function(e) {
      if (e.target.classList.contains('house-input')) {
        highlightRequiredFields();
      }
    });

    document.getElementById('surveyForm').addEventListener('submit', function(e) {
      e.preventDefault();
      hideMessages();

      // ตรวจสอบข้อมูลผู้สำรวจ
      const village = document.getElementById('village').value;
      const surveyor = document.getElementById('surveyor').value.trim();
      const surveyDate = document.getElementById('surveyDate').value;

      if (!village) {
        Swal.fire({
          icon: 'error',
          title: 'กรุณาเลือกหมู่ที่',
          confirmButtonText: 'ตกลง',
        });
        document.getElementById('village').focus();
        return;
      }

      if (!surveyor) {
        Swal.fire({
          icon: 'error',
          title: 'กรุณากรอกชื่อผู้สำรวจ',
          confirmButtonText: 'ตกลง',
        });
        document.getElementById('surveyor').focus();
        return;
      }

      // ตรวจสอบว่ามีข้อมูลบ้านอย่างน้อย 1 บ้าน (แบบใหม่: ต้องมีเลขหลัก หรือ เลขย่อย)
      const houseMainInputs = document.querySelectorAll('input[name^="houseNo_main_"]');
      const houseSubInputs = document.querySelectorAll('input[name^="houseNo_sub_"]');
      let hasValidHouse = false;
      for (let i = 0; i < houseMainInputs.length; i++) {
        const mainVal = houseMainInputs[i].value.trim();
        const subVal = houseSubInputs[i] ? houseSubInputs[i].value.trim() : '';
        if (mainVal || subVal) {
          hasValidHouse = true;
          break;
        }
      }
      if (!hasValidHouse) {
        Swal.fire({
          icon: 'error',
          title: 'กรุณากรอกบ้านเลขที่อย่างน้อย 1 บ้าน',
          confirmButtonText: 'ตกลง',
        });
        return;
      }

      // --- เช็คซ้ำก่อนส่ง ---
      // ใช้ doGet API ที่ Apps Script (ต้องรองรับ CORS และ JSON)
      const getSheetURL = scriptURL + '?action=get'; // เพิ่ม query เพื่อแยก doGet ออกจาก doPost

      fetch(getSheetURL)
        .then(res => res.json())
        .then(rows => {
          // rows: [{village, surveyDate}, ...]
          // เทียบแบบ string ทั้งสองฝั่ง (แปลงเป็น string เพื่อป้องกัน type mismatch)
          const isDuplicate = rows.some(row =>
            String(row.village) === String(village) && String(row.surveyDate) === String(surveyDate)
          );
          if (isDuplicate) {
            Swal.fire({
              icon: 'error',
              title: 'มีการบันทึกข้อมูลหมู่นี้ในวันนี้แล้ว',
              text: 'ไม่สามารถส่งข้อมูลซ้ำได้',
              confirmButtonText: 'ตกลง',
            });
            return;
          }

          // --- Combine houseNo_main_X and houseNo_sub_X into houseNo_X ---
          const formData = new FormData(document.getElementById('surveyForm'));
          for (let i = 1; i <= rowCounter; i++) {
            const main = formData.get(`houseNo_main_${i}`) ? formData.get(`houseNo_main_${i}`).trim() : '';
            const sub = formData.get(`houseNo_sub_${i}`) ? formData.get(`houseNo_sub_${i}`).trim() : '';
            if (main || sub) {
              let combined = main;
              if (main && sub) {
                combined = `${main}/${sub}`;
              } else if (!main && sub) {
                combined = `/${sub}`;
              }
              formData.delete(`houseNo_main_${i}`);
              formData.delete(`houseNo_sub_${i}`);
              formData.append(`houseNo_${i}`, combined);
            } else {
              formData.delete(`houseNo_main_${i}`);
              formData.delete(`houseNo_sub_${i}`);
            }
          }
          // --- End combine ---

          // ส่งข้อมูล
          Swal.fire({
            title: 'กำลังส่งข้อมูล...',
            allowOutsideClick: false,
            didOpen: () => {
              Swal.showLoading();
            }
          });

          fetch(scriptURL, {
            method: 'POST',
            body: formData
          })
          .then(response => {
            Swal.fire({
              icon: 'success',
              title: 'ส่งข้อมูลเรียบร้อยแล้ว',
              text: 'ขอบคุณครับ!',
              confirmButtonText: 'ตกลง',
            });
            setTimeout(() => {
              formContent.innerHTML = '';
              rowCounter = 0;
              addHouse();
              hideMessages();
              const firstHouseInput = document.querySelector('.house-input');
              if (firstHouseInput) firstHouseInput.value = '';
              document.querySelectorAll('.number-input').forEach(input => { input.value = '0'; });
              document.querySelectorAll('.summary-input').forEach(input => { input.value = '0'; });
              document.querySelectorAll('[data-ci-text]').forEach(el => { el.textContent = '0%'; });
              document.querySelectorAll('[data-ci-label]').forEach(el => { el.textContent = ''; });
            }, 2000);
          })
          .catch(error => {
            Swal.fire({
              icon: 'error',
              title: 'เกิดข้อผิดพลาด',
              text: 'กรุณาลองใหม่อีกครั้ง',
              confirmButtonText: 'ตกลง',
            });
          });
        })
        .catch(() => {
          Swal.fire({
            icon: 'error',
            title: 'ไม่สามารถตรวจสอบข้อมูลซ้ำได้',
            text: 'กรุณาลองใหม่อีกครั้ง',
            confirmButtonText: 'ตกลง',
          });
        });
    });
    
    // เพิ่มบ้านแรกเมื่อโหลดหน้า
    addHouse();
    setTimeout(highlightRequiredFields, 100);

    // ตั้งค่าวันที่เป็นวันปัจจุบัน
    const today = new Date();
    const dateString = today.getFullYear() + '-' + 
                      String(today.getMonth() + 1).padStart(2, '0') + '-' + 
                      String(today.getDate()).padStart(2, '0');
    document.getElementById('surveyDate').value = dateString;
    
    // Mockup รายชื่อผู้สำรวจแต่ละหมู่
    const surveyorsByVillage = {
      "1": [
        { value: "นาง สายลม เกียรติยศ", label: "นาง สายลม เกียรติยศ" },
        { value: "นาง ลมัย ท้วมยัง", label: "นาง ลมัย ท้วมยัง" },
        { value: "นาง ด๊อด สุริมา", label: "นาง ด๊อด สุริมา" },
        { value: "นาง สิรินทราภรณ์ มี สุข", label: "นาง สิรินทราภรณ์ มี สุข" },
        { value: "นาย มิ่งขวัญ เนียมศรี", label: "นาย มิ่งขวัญ เนียมศรี" },
        { value: "นาง มะยม จีนย้าย", label: "นาง มะยม จีนย้าย" },
        { value: "นาง สายยัน ปานรุ่ง", label: "นาง สายยัน ปานรุ่ง" },
        { value: "นาง น้ำค้าง กรฤทธิ์", label: "นาง น้ำค้าง กรฤทธิ์" },
        { value: "นาง มาลัย สุขเรือง", label: "นาง มาลัย สุขเรือง" },
        { value: "นาง วันดี จีนย้าย", label: "นาง วันดี จีนย้าย" },
        { value: "นาง สมใจ เหล็กทั่ง", label: "นาง สมใจ เหล็กทั่ง" },
        { value: "นางสาว เสาวนีย์ นวนเปี้ย", label: "นางสาว เสาวนีย์ นวนเปี้ย" },
        { value: "นาง สุธาสินี บุตรบุญ", label: "นาง สุธาสินี บุตรบุญ" },
        { value: "นางสาว ลักษมี จีนย้าย", label: "นางสาว ลักษมี จีนย้าย" },
        { value: "นาง สุธาสินี นาคเทศ", label: "นาง สุธาสินี นาคเทศ" },
        { value: "นาย ทองศุกร์ จันทร์ดำ", label: "นาย ทองศุกร์ จันทร์ดำ" }
      ],
      "2": [
        { value: "นาย อุทิศ อินอิว", label: "นาย อุทิศ อินอิว" },
        { value: "นาง น้ำตาล จันทร์ดำ", label: "นาง น้ำตาล จันทร์ดำ" },
        { value: "นาย ตวย ทองคำ", label: "นาย ตวย ทองคำ" },
        { value: "นางสาว ปรัชญา จีนย้าย", label: "นางสาว ปรัชญา จีนย้าย" },
        { value: "นาง ทับทิม เกตุประดิษฐ", label: "นาง ทับทิม เกตุประดิษฐ" },
        { value: "นาง แฉล้ม เหล็กสิงห์", label: "นาง แฉล้ม เหล็กสิงห์" },
        { value: "นาย ด่วน แสนสุภา", label: "นาย ด่วน แสนสุภา" },
        { value: "นางสาว ภัทรวดี พูลพิชัย", label: "นางสาว ภัทรวดี พูลพิชัย" },
        { value: "นาง กุล จีนย้าย", label: "นาง กุล จีนย้าย" },
        { value: "นาง เกียร์ จีนย้าย", label: "นาง เกียร์ จีนย้าย" },
        { value: "นาง ละมัย เหล็กสิงห์", label: "นาง ละมัย เหล็กสิงห์" },
        { value: "นาย ลำดวน เหล็กสิงห์", label: "นาย ลำดวน เหล็กสิงห์" },
        { value: "นาง น้ำนอง บัวพาเรือง", label: "นาง น้ำนอง บัวพาเรือง" },
        { value: "นาย สุขอนันต์ ย้ายหน่าย", label: "นาย สุขอนันต์ ย้ายหน่าย" },
        { value: "นาง นนต์ แป้นเพ็ชร", label: "นาง นนต์ แป้นเพ็ชร" },
        { value: "นาง กัญญา แสนสุภา", label: "นาง กัญญา แสนสุภา" },
        { value: "นาง น้ำผึ้ง เหล็กสิงห์", label: "นาง น้ำผึ้ง เหล็กสิงห์" },
        { value: "นาง ไพ พุ่มเทียน", label: "นาง ไพ พุ่มเทียน" },
        { value: "นาง ออด แป้นเพ็ชร", label: "นาง ออด แป้นเพ็ชร" },
        { value: "นาง ติ้ม บุญมีโพธิ์", label: "นาง ติ้ม บุญมีโพธิ์" },
        { value: "นาง แอน สิงห์คาร", label: "นาง แอน สิงห์คาร" },
        { value: "นาง พิม จันทร์ดำ", label: "นาง พิม จันทร์ดำ" },
        { value: "นาง ส้มปอย บุตรดา", label: "นาง ส้มปอย บุตรดา" },
        { value: "นาง สำเภา เงินพล", label: "นาง สำเภา เงินพล" },
        { value: "นางสาว นิพา เนียมสี", label: "นางสาว นิพา เนียมสี" },
        { value: "นาง เสวย แป้นเพ็ชร", label: "นาง เสวย แป้นเพ็ชร" },
        { value: "นาง คล้าย พัดจันทร์หอม", label: "นาง คล้าย พัดจันทร์หอม" },
        { value: "นาง คำนึง เหล็กสิงห์", label: "นาง คำนึง เหล็กสิงห์" },
        { value: "นาง ยอดขวัญ ถิ่นพยัคฆ์", label: "นาง ยอดขวัญ ถิ่นพยัคฆ์" },
        { value: "นาง ศศิวิมล ทองคำ", label: "นาง ศศิวิมล ทองคำ" },
        { value: "นาง กาหลง จันทร์ดำ", label: "นาง กาหลง จันทร์ดำ" }
      ],
      "3": [
        { value: "นาง กาเหว่า เหล็กสิงห์", label: "นาง กาเหว่า เหล็กสิงห์" },
        { value: "นาง สายญู บุตรเจริญ", label: "นาง สายญู บุตรเจริญ" },
        { value: "นาย สิงห์ วันอ่อง", label: "นาย สิงห์ วันอ่อง" },
        { value: "นาง ดาวเรือง อิ่มเพ็ง", label: "นาง ดาวเรือง อิ่มเพ็ง" },
        { value: "นาง ไพวัล ชัยชนะ", label: "นาง ไพวัล ชัยชนะ" },
        { value: "นาง อัญณิมา อิ่มเพ็ง", label: "นาง อัญณิมา อิ่มเพ็ง" },
        { value: "นาง สุริกิจ เหล็กสิงห์", label: "นาง สุริกิจ เหล็กสิงห์" },
        { value: "นาย สมคิด เหล็กทั่ง", label: "นาย สมคิด เหล็กทั่ง" },
        { value: "นาย พ้ง เพ็งคง", label: "นาย พ้ง เพ็งคง" },
        { value: "นาง เด่นนภา เขียวดี", label: "นาง เด่นนภา เขียวดี" },
        { value: "นาง ดวงนภา เขียวดี", label: "นาง ดวงนภา เขียวดี" },
        { value: "นาง สุพัตรา ผดุงเวียง", label: "นาง สุพัตรา ผดุงเวียง" },
        { value: "นาง สมบุญ บุญคง", label: "นาง สมบุญ บุญคง" },
        { value: "นาง ดาราวรรณ ท้วมยัง", label: "นาง ดาราวรรณ ท้วมยัง" },
        { value: "นาง ดวงตา จีนย้าย", label: "นาง ดวงตา จีนย้าย" },
        { value: "นาง สุภาวดี มีจอ", label: "นาง สุภาวดี มีจอ" },
        { value: "นาง วรรณสิริ ไกรกิจราษฎร์", label: "นาง วรรณสิริ ไกรกิจราษฎร์" },
        { value: "นาง จันพร เหล็กสิงห์", label: "นาง จันพร เหล็กสิงห์" },
        { value: "นางสาว ฝากจิตร จีนย้าย", label: "นางสาว ฝากจิตร จีนย้าย" },
        { value: "นาง จันทร์ทิพย์ นันคำ", label: "นาง จันทร์ทิพย์ นันคำ" },
        { value: "นาง บุญธรรม เพ็งคง", label: "นาง บุญธรรม เพ็งคง" },
        { value: "นางสาว อุไรรัตน์ พัดจันทร์หอม", label: "นางสาว อุไรรัตน์ พัดจันทร์หอม" },
        { value: "นาง ไฝ เขียวดี", label: "นาง ไฝ เขียวดี" },
        { value: "นาง เครือ เม่นอยู่", label: "นาง เครือ เม่นอยู่" },
        { value: "นางสาว วันเพ็ญ ปานรุ่ง", label: "นางสาว วันเพ็ญ ปานรุ่ง" }
      ],
      "4": [
        { value: "นาย น้อย ภู่ระหงษ์", label: "นาย น้อย ภู่ระหงษ์" },
        { value: "นาย โกมล อินอิว", label: "นาย โกมล อินอิว" },
        { value: "นาย เชิด เพ็ชรดี", label: "นาย เชิด เพ็ชรดี" },
        { value: "นาย บุญเลิศ มากมี", label: "นาย บุญเลิศ มากมี" },
        { value: "นาย ยอง พุ่มเทียน", label: "นาย ยอง พุ่มเทียน" },
        { value: "นาย ถ้วน เกิดแป้น", label: "นาย ถ้วน เกิดแป้น" },
        { value: "นาย คำล่า สุขเจริญ", label: "นาย คำล่า สุขเจริญ" },
        { value: "นาย สมนึก เอี่ยมบุรี", label: "นาย สมนึก เอี่ยมบุรี" },
        { value: "นาย วิโรจน์ มากมี", label: "นาย วิโรจน์ มากมี" },
        { value: "นาย รุ่ง แสนสุภา", label: "นาย รุ่ง แสนสุภา" },
        { value: "นาย วิสูตร์ พุ่มเทียน", label: "นาย วิสูตร์ พุ่มเทียน" },
        { value: "นางสาว ภัทรวดี กรแก้ว", label: "นางสาว ภัทรวดี กรแก้ว" },
        { value: "นางสาว จอมขวัญ มาเต", label: "นางสาว จอมขวัญ มาเต" },
        { value: "นาย จีรวัฒน์ มากมี", label: "นาย จีรวัฒน์ มากมี" },
        { value: "นางสาว ทัศนีย์ อินอิว", label: "นางสาว ทัศนีย์ อินอิว" },
        { value: "นางสาว ทิพยาภรณ์ บุตรดา", label: "นางสาว ทิพยาภรณ์ บุตรดา" }
      ],
      "5": [
        { value: "นาง เฉลย ดำงาม", label: "นาง เฉลย ดำงาม" },
        { value: "นาง ดอกเทียน จีนย้าย", label: "นาง ดอกเทียน จีนย้าย" },
        { value: "นาง กรรณิกา จงบริบูรณ์", label: "นาง กรรณิกา จงบริบูรณ์" },
        { value: "นาง สบง ทองคำ", label: "นาง สบง ทองคำ" },
        { value: "นาง ปิ่น จันทร์ดำ", label: "นาง ปิ่น จันทร์ดำ" },
        { value: "นาง ฐิติยา บุตรบุญ", label: "นาง ฐิติยา บุตรบุญ" },
        { value: "นาง อ้อยใจ มาโพธิ์", label: "นาง อ้อยใจ มาโพธิ์" },
        { value: "นาย บรรลุ เอี่ยมสวัสดิ์", label: "นาย บรรลุ เอี่ยมสวัสดิ์" },
        { value: "นาง สินาภรณ์ เหล็กสิงห์", label: "นาง สินาภรณ์ เหล็กสิงห์" },
        { value: "นางสาว ขวัญเรียม ท้วมยัง", label: "นางสาว ขวัญเรียม ท้วมยัง" },
        { value: "นางสาว ประหยัด อิ่มเพ็ง", label: "นางสาว ประหยัด อิ่มเพ็ง" },
        { value: "นาย ฉลอมชัย เขียวดี", label: "นาย ฉลอมชัย เขียวดี" },
        { value: "นาง ชบา อิ่มเพ็ง", label: "นาง ชบา อิ่มเพ็ง" },
        { value: "นาย ณัฐพงษ์ เงินพล", label: "นาย ณัฐพงษ์ เงินพล" },
        { value: "นางสาว มยุรา สามงามมี", label: "นางสาว มยุรา สามงามมี" },
        { value: "นาง สมจิตร บุญมา", label: "นาง สมจิตร บุญมา" },
        { value: "นาง วีระ ศรีทอง", label: "นาง วีระ ศรีทอง" },
        { value: "นาง สร้อยม่าน ศรีภิรมณ์", label: "นาง สร้อยม่าน ศรีภิรมณ์" },
        { value: "นาง จินตนา อิ่มเพ็ง", label: "นาง จินตนา อิ่มเพ็ง" },
        { value: "นาง เสน่ห์ ดำสนิท", label: "นาง เสน่ห์ ดำสนิท" },
        { value: "นาง วาสนา อินรุ่ง", label: "นาง วาสนา อินรุ่ง" },
        { value: "นาง สายลวด คัญทับ", label: "นาง สายลวด คัญทับ" },
        { value: "นาง ศิริรัตน์ อิ่มเพ็ง", label: "นาง ศิริรัตน์ อิ่มเพ็ง" },
        { value: "นาง ละมุด จันทร์ดำ", label: "นาง ละมุด จันทร์ดำ" },
        { value: "นาง มะลิวัลย์ แป้นเพ็ชร", label: "นาง มะลิวัลย์ แป้นเพ็ชร" },
        { value: "นาง นริศรา สิงห์คาร", label: "นาง นริศรา สิงห์คาร" },
        { value: "นาง สายทอง อิ่มเพ็ง", label: "นาง สายทอง อิ่มเพ็ง" },
        { value: "นางสาว อมรรัตน์ เอี่ยมสวัสดิ์", label: "นางสาว อมรรัตน์ เอี่ยมสวัสดิ์" },
        { value: "นาง จิราวรรณ กาดกอเสริม", label: "นาง จิราวรรณ กาดกอเสริม" },
        { value: "นาง ฉัตร อินอิว", label: "นาง ฉัตร อินอิว" },
        { value: "นาง นฤมล จันทร์ดำ", label: "นาง นฤมล จันทร์ดำ" }
      ],
      "6": [
        { value: "นาง จั่น เหล็กสิงห์", label: "นาง จั่น เหล็กสิงห์" },
        { value: "นาง ชะลอ แป้นต่วน", label: "นาง ชะลอ แป้นต่วน" },
        { value: "นาง ดำเนิน เอี่ยมสวัสดิ์", label: "นาง ดำเนิน เอี่ยมสวัสดิ์" },
        { value: "นาง อันชัน อิ่มเพ็ง", label: "นาง อันชัน อิ่มเพ็ง" },
        { value: "นาย ประโยชน์ เนียมสี", label: "นาย ประโยชน์ เนียมสี" },
        { value: "นาย สังเวียน จันทร์ดำ", label: "นาย สังเวียน จันทร์ดำ" },
        { value: "นาง รัญญา แดงมี", label: "นาง รัญญา แดงมี" },
        { value: "นาง บรรหยัด เหล็กทั่ง", label: "นาง บรรหยัด เหล็กทั่ง" },
        { value: "นาง ก้านแก้ว จีนย้าย", label: "นาง ก้านแก้ว จีนย้าย" },
        { value: "นาง วาริพิน กูบโคกกรวด", label: "นาง วาริพิน กูบโคกกรวด" },
        { value: "นาง สมทรง จีนย้าย", label: "นาง สมทรง จีนย้าย" },
        { value: "นาง จินตนา เหล็กสิงห์", label: "นาง จินตนา เหล็กสิงห์" },
        { value: "นาง นอม ภู่ผิว", label: "นาง นอม ภู่ผิว" },
        { value: "นางสาว กนกวรรณ อินอิว", label: "นางสาว กนกวรรณ อินอิว" },
        { value: "นาง วณิชชา จีนย้าย", label: "นาง วณิชชา จีนย้าย" },
        { value: "นาง พรลดา อินอิว", label: "นาง พรลดา อินอิว" },
        { value: "นาง ดอกสร้อย สดนามอญ", label: "นาง ดอกสร้อย สดนามอญ" },
        { value: "นาง ลูกน้ำ เหล็กสิงห์", label: "นาง ลูกน้ำ เหล็กสิงห์" },
        { value: "นาง กำไร เหล็กสิงห์", label: "นาง กำไร เหล็กสิงห์" },
        { value: "นาง จิรัฐติกาล ทองคำ", label: "นาง จิรัฐติกาล ทองคำ" },
        { value: "นางสาว หนึ่งฤทัย นาคเทศ", label: "นางสาว หนึ่งฤทัย นาคเทศ" }
      ],
      "7": [
        { value: "นาง สุลี เหล็กสิงห์", label: "นาง สุลี เหล็กสิงห์" },
        { value: "นาย กล้า ปานรุ่ง", label: "นาย กล้า ปานรุ่ง" },
        { value: "นาง เด่น แก้วหลำ", label: "นาง เด่น แก้วหลำ" },
        { value: "นาง ขยัน ทองคำ", label: "นาง ขยัน ทองคำ" },
        { value: "นาง ดอกพุฒ ปกรณ์ธาดา", label: "นาง ดอกพุฒ ปกรณ์ธาดา" },
        { value: "นาง กัลยา ปกรณ์ธาดา", label: "นาง กัลยา ปกรณ์ธาดา" },
        { value: "นาง ทิม อ่อนละมัย", label: "นาง ทิม อ่อนละมัย" },
        { value: "นาง สุภัค ด้วงแจ่ม", label: "นาง สุภัค ด้วงแจ่ม" },
        { value: "นางสาว ชม้อย พรมมั่น", label: "นางสาว ชม้อย พรมมั่น" },
        { value: "นาง ศรีนวล เหล็กสิงห์", label: "นาง ศรีนวล เหล็กสิงห์" },
        { value: "นาง ประดล บุญเหม", label: "นาง ประดล บุญเหม" },
        { value: "นาง ม่านฟ้า เทียนทอง", label: "นาง ม่านฟ้า เทียนทอง" },
        { value: "นาง วิไล ท้วมยัง", label: "นาง วิไล ท้วมยัง" },
        { value: "นางสาว กฤษณา อิ่มเพ็ง", label: "นางสาว กฤษณา อิ่มเพ็ง" },
        { value: "นาง บุษยา ทองพับ", label: "นาง บุษยา ทองพับ" },
        { value: "นาง ยุพิน ทองคำ", label: "นาง ยุพิน ทองคำ" },
        { value: "นาง จุฑามาศ ทองคำ", label: "นาง จุฑามาศ ทองคำ" },
        { value: "นาง บัวแก้ว พัดจันทร์หอม", label: "นาง บัวแก้ว พัดจันทร์หอม" },
        { value: "นาง จินดาดล เหล็กสิงห์", label: "นาง จินดาดล เหล็กสิงห์" },
        { value: "นางสาว ณัฐชา ขุนหมื่น", label: "นางสาว ณัฐชา ขุนหมื่น" },
        { value: "นาย ดอกรัก จันทร์หลำผล", label: "นาย ดอกรัก จันทร์หลำผล" },
        { value: "นาง ฉวี เหล็กสิงห์", label: "นาง ฉวี เหล็กสิงห์" },
        { value: "นางสาว หงหยก จีนย้าย", label: "นางสาว หงหยก จีนย้าย" }
      ]
    };

    // เมื่อเลือกหมู่ที่ ให้แสดงชื่อผู้สำรวจเฉพาะหมู่นั้น
    document.getElementById('village').addEventListener('change', function() {
      const village = this.value;
      const surveyorSelect = document.getElementById('surveyor');
      surveyorSelect.innerHTML = '<option value="">เลือกผู้สำรวจ</option>';
      if (surveyorsByVillage[village]) {
        surveyorsByVillage[village].forEach(person => {
          const opt = document.createElement('option');
          opt.value = person.value;
          opt.textContent = person.label;
          surveyorSelect.appendChild(opt);
        });
      }
    });

    // ทำให้ฟอร์มเป็น global function
    window.deleteHouse = deleteHouse;
    window.calculateSummary = calculateSummary;

    // เพิ่ม event delegation สำหรับบังคับกรอก "รายละเอียดอื่นๆ" ก่อนใส่จำนวน
    document.addEventListener('input', function(e) {
      // ในอาคาร - อื่นๆ
      if (e.target.classList.contains('in-other-amount')) {
        const groupKey = e.target.getAttribute('data-other-amount');
        const detailInput = e.target.closest('.location-group').querySelector('.in-other-detail');
        const warning = e.target.closest('.location-group').querySelector('.in-other-warning');
        if (detailInput && !detailInput.value.trim()) {
          e.target.value = '';
          if (warning) {
            warning.textContent = 'กรุณากรอกรายละเอียดอื่นๆ ก่อนใส่จำนวน';
            warning.style.display = 'block';
          }
        } else if (warning) {
          warning.textContent = '';
          warning.style.display = 'none';
        }
      }

      // นอกอาคาร - อื่นๆ
      if (e.target.classList.contains('out-other-amount')) {
        const groupKey = e.target.getAttribute('data-other-amount');
        const detailInput = e.target.closest('.location-group').querySelector('.out-other-detail');
        const warning = e.target.closest('.location-group').querySelector('.out-other-warning');
        if (detailInput && !detailInput.value.trim()) {
          e.target.value = '';
          if (warning) {
            warning.textContent = 'กรุณากรอกรายละเอียดอื่นๆ ก่อนใส่จำนวน';
            warning.style.display = 'block';
          }
        } else if (warning) {
          warning.textContent = '';
          warning.style.display = 'none';
        }
      }
    });
    // --- Number input UX: show 0 as default, clear on focus, restore 0 if empty ---
    function handleNumberInputFocus(e) {
      if (e.target.classList.contains('number-input')) {
        // Only clear if value is exactly 0
        if (e.target.value === '0') {
          e.target.value = '';
        }
      }
    }

    function handleNumberInputBlur(e) {
      if (e.target.classList.contains('number-input')) {
        // If left empty, restore 0
        if (e.target.value === '' || e.target.value === null) {
          e.target.value = '0';
        }
      }
    }

    function handleNumberInputInput(e) {
      if (e.target.classList.contains('number-input')) {
        // Prevent multiple leading zeros
        if (/^0\d+/.test(e.target.value)) {
          e.target.value = e.target.value.replace(/^0+/, '');
        }
        // If user deletes all, keep empty (blur will restore 0)
      }
    }

    // Attach event listeners (delegated)
    document.addEventListener('focusin', handleNumberInputFocus);
    document.addEventListener('blur', handleNumberInputBlur, true);
    document.addEventListener('input', handleNumberInputInput);
    // --- End Number input UX ---
  </script>
</body>
</html>
