# Goracle-Node

Cấu hình khuyến nghị:
    
    Cpu: 1-2 cores
    Ram: 4gb
    Storage: 10gb SSD
    Ubuntu: 20.04+

Cộng đồng chạy node VietNam:

    https://t.me/NodeValidatorVietNam
    
1/ Cập nhật hệ thống:

    sudo apt update && apt upgrade -y
    
2/ Cài đặt Docker:

    sudo apt-get update
    sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
    sudo mkdir -m 0755 -p /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
    sudo apt-get update -y
    
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
    
3/ Cài đặt bộ cài node:

    sudo wget -qP /usr/bin/ https://staging.dev.goracle.io/downloads/latest-staging/goracle && sudo chmod u+x /usr/bin/goracle
    
Nhập thông tin node:

    sudo goracle init
    
Nhấn theo các bước sau:

    Y
    Y
    Y
    Enter
    
Vào trang web tải Ví IOS/Android

    https://web.perawallet.app/
    
    Note: Lưu lại 25 kí tự đặc biệt

Faucet token testnet:

    https://bank.testnet.algorand.network/

Vào Dashboard dự án, kết nối ví:

    https://testnet-app.goracle.io/nodes/optin
    
Lưu Ý: Đoạn này quan trọng, chờ cho nhận được token testnet rồi làm tiếp.

    Check kiểm tra Coin nhận được chưa bằng cách vào Pera Wallet -> Setting -> Developer -> Node Setting -> Testnet -> Kiểm tra 

4/ Quay lại màn hình cài Node; Dán địa chỉ ví vào dòng: 

    ENTER YOUR ACCOUNT ALGORAND WALLET:BL36IZCQTGWP4JFBWYCOUIUQBB4DKHJA7OQ6MQEHYNDKBZYJTQ
    
Sẽ ra dòng: please register account link; chỉ lấy đoạn mã phía sau dấu =

Ví dụ:
  
    GPEJUGD7YW2UZRHZJWHKVRVEVORWZGDDXJGMDPUPUH7S3LK6H2MUWX

Copy đoạn code này dán vào Dashboard -> Node Portal -> Enter Participation Key, nhấn REGISTER

5/ Add stake và chạy Node:

    Get Test Gora
    
Nếu không nhận được mã CODE về Mail, cứ bỏ qua bước này.

    Add stake
    
Nhập số lượng: ví dụ 10.000
    
    Add stake
    
Chạy node:

    sudo goracle docker-start --background
    
Check log:

    docker logs -f goracle-nr
