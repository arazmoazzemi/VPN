## CLOUDFLARE WARP ON UBUNTU

---
[Cloudflare WARP packages](https://pkg.cloudflareclient.com/#ubuntu])
---

### Add cloudflare gpg key
```bash
curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg
```
### Add this repo to your apt repositories
```bash
echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/cloudflare-client.list
```

### Install
```bash
sudo apt-get update && sudo apt-get -y install cloudflare-warp
```
---
[Using WARP Client](https://developers.cloudflare.com/warp-client/get-started/linux/)
---

### Initial Connection
### To connect for the very first time:

```bash
warp-cli --help

warp-cli registration new

warp-cli connect

warp-cli registration show

# Test
curl https://www.cloudflare.com/cdn-cgi/trace/
```

### Switching modes
```bash
warp-cli set-mode --help

warp-cli help set-mode doh

warp-cli registration show
```
---

### Install iptables
```bash
sudo apt-get -y install iptables-persistent
sudo netfilter-persistent save
sudo systemctl enable netfilter-persistent
```

If you mistakenly enterd the initial input values of iptables, you can rewrite the tables again with the following command.  
The provided commands reset the default policies for the INPUT, OUTPUT, and FORWARD chains to ACCEPT, and then flush all the rules from all the chains.

```bash
iptables -P INPUT ACCEPT
iptables -P OUTPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -F

```
### We have two interfaces for provide nat , CloudflareWARP and ens32

```
iptables -t nat -A POSTROUTING -o CloudflareWARP -j MASQUERADE
iptables -A FORWARD -i CloudflareWARP -o ens32 -m state --state RELATED,ESTABLISHED -j ACCEPT
iptables -A FORWARD -i ens32 -o CloudflareWARP -j ACCEPT

sudo iptables -L -v -n | more
```
---


---
sudo apt-get update && sudo apt-get install -y python3.10 git pip

git clone https://github.com/TheCaduceus/WARP-UNLIMITED-ADVANCED.git

pip install -r requirements.txt
cd WARP-UNLIMITED-ADVANCED/


warp-cli registration show

# Device ID: e4952ae4-364d-408e-8d23-d2c8d822ecc0


nano config.py




python3 warp-plus.py


cat runtime-log.txt

---


### Warp+ licences, It may not work, You will find it
---
```bash
warp-cli registration license 41x8Cg2j-rYu7C123-D2jbE943
warp-cli registration license 0In49xR7-PXR14G95-261KxgO0
warp-cli registration license 4q81P5wN-C5du136F-L3xJ058v
warp-cli registration license 1302udmR-0492VqMy-8Q4PIx27
warp-cli registration license 74XmO3e0-OS516yJ7-HaE2K365
warp-cli registration license VW15Hz60-8tz067Yj-267k8UWm
warp-cli registration license 0M7tO49a-4e5xd19h-795efY2k
warp-cli registration license t3syz679-8X4pI65v-B57i6X8x
warp-cli registration license q6Q31l9Z-FcGv3129-83Kl4fp5
warp-cli registration license PA5349RE-RZ8M097X-0A85kE2B

warp-cli registration license 690pLB7U-7gz8T04V-48lu9QD0
warp-cli registration license y89z3X2B-69fMg80l-X531AH6h
warp-cli registration license 2kj896Ct-61ZH3kK5-uO581P3w
warp-cli registration license 9HKS81x4-rN9405KG-FD4273wY
warp-cli registration license 0m8Yg2z4-9d371IWs-90HLJU24
warp-cli registration license 92z1Ywb7-5XO36PF1-1E6jk5g7
warp-cli registration license 18QE4oP7-Dt863w7L-d6w2G35I
warp-cli registration license S5647wQi-6lb1S49v-y3EeY478
warp-cli registration license l159nQ0N-f4T9P51s-c2a8VQ90
warp-cli registration license 0V35CUL1-k4zA327I-5o2tL1N3

warp-cli registration license 9Xi5r71E-3myw765H-7ib3uO86
warp-cli registration license 452HljE9-1aTJ782Y-54J0f2qW
warp-cli registration license 7Wf6p9F3-V9P571Ab-021qC4Ur
warp-cli registration license d40F5r3O-8s9E17qg-h38Il15M
warp-cli registration license D123a5uX-843zF5qj-9oX068DG
warp-cli registration license i4P81x2U-3la270Rr-157gI6WS
warp-cli registration license Y40o96Ms-31fK45Ds-a5679CLs
warp-cli registration license O95QEk34-2g0Mfv39-X51BAF80
warp-cli registration license 897sgC0R-h6g350Tj-G983Q4mL
warp-cli registration license H6qz35o2-95gaO4T2-42JM1md5

warp-cli registration license sx2T95w7-GU72Nn96-p608jdm9
warp-cli registration license n2760sNc-2H1J8W0s-2Yo5f3k6
warp-cli registration license 9Yb17i3F-3zI64T0F-X03Mu91G
warp-cli registration license 0hS8ki67-3nfN9c81-721ZadO6
warp-cli registration license 289sn7WM-s6NX450o-lWcK7095
warp-cli registration license 73m6sB1W-3g608XPO-X50GDb72
warp-cli registration license I68C9Lt3-5c9D62VI-Oc24R19u
warp-cli registration license 837pt0os-3i8km75f-9US345Ik
warp-cli registration license 69ecj28n-iC5a78y1-Rd0295bl
warp-cli registration license 18ctoP74-71Oi95Yd-l5KTF142
warp-cli registration license 1u4z9o8T-84S9XI1N-Uj914Hs2

warp-cli registration license 24IUlm86-H85C9j0w-g7ip23O9
warp-cli registration license 78U93cZg-5D9fmx10-eH59W2h1
warp-cli registration license W402tPT1-72M6Uv3i-5KFm0x34
warp-cli registration license IP2E8R51-20MHL6k7-l8U7SQ10
warp-cli registration license 6YH578cd-Lqm8z796-87YR1Ui0
warp-cli registration license 8um5DC12-046C2YzE-29kpG14y
warp-cli registration license Z6079IsJ-oV45O1T6-oJz8O475
warp-cli registration license s0iu6r24-j4pE398N-Q9Vl46A1
warp-cli registration license m24k3oT1-09Lqsf35-16b0cAi4


warp-cli registration license Uyl41h70-L8d2O73i-g83fy4p6
warp-cli registration license 6N2r90VE-4908howR-U14es69m
warp-cli registration license 73fo6C9r-042DgSP9-0369HVQm
warp-cli registration license 3zqO15x8-UE3il721-4V06FE8Z
warp-cli registration license D8z7J96O-7Pe8wu14-P7o62My8
warp-cli registration license 5MG82vz9-7jE1xl86-XO1532rk
warp-cli registration license 8O54Ixc9-01PH9b5t-Ffp562q4
warp-cli registration license 3m4VF50h-tf4758TI-9a08Rrc1
warp-cli registration license L1s8G52Z-E86Ut25V-93t14ncl
warp-cli registration license z158sy4J-74Kz8lh9-QCS3O241

warp-cli registration license 9O84Mpb0-1n467WAd-3g479XSF
warp-cli registration license 18yb2U3T-582R4WAB-98ut67Kc
warp-cli registration license 9lQa3h50-17e5pf0t-z126TsE3
warp-cli registration license 8H7yET54-sz5V27L0-eR2Nh457
warp-cli registration license a72AgN14-o8Ss09q4-C7Z09e3k
warp-cli registration license TqeJ9250-G1v9W08T-0W7Ec95D
warp-cli registration license yrg860K2-917Odq6j-i61o5EX7
warp-cli registration license 52ZD3JF4-W697d0Vz-w65ds2W7
warp-cli registration license l5JS718C-i57mW62p-08t9dgw1
warp-cli registration license 8p3NPA46-H80p3a9l-VaG0N721

warp-cli registration license 7HE5T43p-2973tuDg-81mFe0T6
warp-cli registration license 7HE5T43p-2973tuDg-81mFe0T6
warp-cli registration license n16Fg5z2-5Q1uf2q0-J29i1p3F
warp-cli registration license bU5M37X9-91KA34Zk-ig6X983G
warp-cli registration license 57p9rdM6-DH0678hB-KqRX7614
warp-cli registration license BR8N37K1-57A64HFN-VhF9G065
warp-cli registration license V41WX53h-S2wO9W08-K7S042xv
warp-cli registration license O16i5bm0-5g7cs6L2-6nN2x1l4
warp-cli registration license gi9Z265t-ko2zU485-18VW2e7U
warp-cli registration license 0742srFP-0JV46c8Y-1a28q7kS

warp-cli registration license d92Rl1w0-S0k451Um-EK9s2R54
warp-cli registration license bE04xQ28-t71Z3Ea9-7p2we83Q
warp-cli registration license IP2096zu-6xskl429-35xY8U4L
warp-cli registration license T485yYz2-71e8mj0G-Q35Z61gv
warp-cli registration license c6507nNG-P48hGa06-62BA57sf
warp-cli registration license r6JA3N75-GZ5w07t6-cXi782h3
warp-cli registration license oj698cU2-1Gkr478m-J0Q4Uq35
warp-cli registration license oB86vZ02-2BZo53A7-y7F293wP
warp-cli registration license G7S21c8K-Ge0a61A5-F8E4K2T6
warp-cli registration license 1H7Tjm26-n1j567EO-Y6Oq817n

warp-cli registration license tL9X086w-h764V2ci-8le569gq
warp-cli registration license vb54V3s6-40LO12rE-09Fif52m
warp-cli registration license 8L60g4hQ-a8d4lK19-z4318sRp
warp-cli registration license c807q1ST-F9h5U6g4-P1Ax6t95
warp-cli registration license tk0w194a-1W26ogm4-0z5MAt87
warp-cli registration license 291aG5BU-e849Ar3d-528FpvA0
warp-cli registration license uO96p3F4-8X3Qe7y4-Bw9517qH
warp-cli registration license dN4357lD-6895OToC-0ot18FR9
warp-cli registration license 5P9js84r-69n8m4Fa-4WLG1h35
warp-cli registration license 4zXZ6H51-0hz91xc4-2a157MxQ

warp-cli registration license SGA752T0-zi758X6t-9H1P23Ms
warp-cli registration license t639Fz2o-z3pn0K84-uM4Z37h1
warp-cli registration license fh26N39L-9XOn815W-xJ7o10z9
warp-cli registration license 2rkn961C-s9e165uO-xE9C36Y1
warp-cli registration license 2y1CxB49-a20I1jO3-h6pn20I4
warp-cli registration license 7dw0Sn15-70mc6GY5-14mzS9t8
warp-cli registration license w7e3t10Z-u8Gg160t-Ef50j72U
warp-cli registration license t6I4GJ01-21Fr45Xj-7D5eL12B
warp-cli registration license 0d43J7Pi-N87L4i2q-871IA3WZ
warp-cli registration license tWR6Q782-6x894rBG-hFQ15Z03

warp-cli registration license Td46H58W-6gz4mS01-g953Ym4i
warp-cli registration license 06So5b3F-m8V94MT0-5n2B0AO6
warp-cli registration license 0HY7X1V3-V34rpI18-YVQ6851w
warp-cli registration license qb5H38P2-Fa5j274i-3Z974yKS
warp-cli registration license zR9k67x3-5P4ta26i-5Rdh9t48
warp-cli registration license c27D9OQ1-8xW342nD-3ai5u4p0
warp-cli registration license 9W2OA1D8-0L16bZ4u-5P6Yw1Z8
warp-cli registration license RD5903Og-yJ7i25l6-70d1Kg4s
warp-cli registration license 13F6ic9Z-4963CtQf-9Z8a35lN
warp-cli registration license O5Y46G1E-K397w6Sk-C978BVt3
```

---
