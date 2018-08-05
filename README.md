# -
環境安裝教學

LNMP 環境安裝教學

IP : select concat(payment_gateway.id,',',payment_gateway.name,',',inet_ntoa(payment_gateway_bind_ip.ip)) from payment_gateway inner join payment_gateway_bind_ip on payment_gateway.id = payment_gateway_bind_ip.payment_gateway_id

心得:
隨付:
用訂單號查詢return.log，發現是返回驗證失敗，因此詢問業主的公私鑰是否設置正確

聚方雲:
需修改參數settleCycle=0，這是應該寫成用額外參數設定，不應該寫死的

速付:
新增回調IP

萬通支付:
查看回傳的錯誤代碼發現是支付發不出去，所以去查看NGINX的PAYMENT.ACCESS.LOG，發現三筆發了超過10秒就自動斷開了
單純對提交網址發CURL也發現無法使用了，

中銀支付:
需更換提交網址，給的商號而對方提供的商號無法使用，要等對方提供新的商號，後來又發現我們就有的接口參數跟對方提供的對不上

誠優支付:
後臺收到款項我們的系統卻沒加上額度，8/10號

E匯支付(商號:180714369141):
後臺無PAY網址，查看返回參數的IP並無相同，須新增IP白名單

信付通:
參數改成UNIONQRPAY isApp=APP
