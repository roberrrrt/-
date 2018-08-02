# -
環境安裝教學

LNMP 環境安裝教學


1.客服有給商號，出現連線問題的，如果有給出錯誤訊息，
  根據錯誤訊息去故障排除，可以到DEMO頁看該支付平台的
  詳細資料，然後找出他的verify_url(支付網址)跟LABEL(程式碼名稱)
  接著到對外LOG機，先連上正式站，然後跳到結尾是41OR42的PAYMENT LOG機
  到/var/log/nginx/pink.access.log
  然後 $grep '關鍵字串' pink.access.log，去看LOG說出現什麼問題

