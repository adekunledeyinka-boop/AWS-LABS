
# Day 2: Security Group & SSH in AWS

## Concept
- Security Group (SG) = virtual firewall for EC2
- SSH = secure remote login to server
- Key Pair (.pem) = private key for login

## Real-Life Scenario
- SaaS company developers access servers securely
- Only trusted IPs (office or VPN) allowed
- Protects servers from unauthorized access

## Security Group Setup (Planned)
1. Name: test_sg
2. Description: testsecurity group for SSH
3. VPC: default
4. Inbound rule:
   - Type: SSH
   - Protocol: TCP
   - Port: 22
   - Source: My IP
5. Outbound rule: default (all traffic allowed)

## EC2 Launch Plan
- AMI: Amazon Linux 2
- Instance Type: t3.micro
- Key Pair:test_kp.pem
- Security Group: test_sg
- Subnet: default

## SSH Command (After Launch)
```bash
ssh -i xfusion-kp.pem ec2-user@<Public-IP>
