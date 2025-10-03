def calculate_contract_advanced():
    print("=== 北辰团队金融合约计算器 ===")
    
    # 输入账号总资产
    total_assets = float(input("请输入您的账号总资产 (USD): "))
    
    # 选择方向（做多或做空）
    direction = input("请选择方向（多/空）: ")
    if direction not in ["多", "空"]:
        print("无效的选择，请输入 '多' 或 '空'")
        return
    
    # 输入杠杆倍数
    leverage = float(input("请输入杠杆倍数: "))
    
    # 输入风险控制
    risk_amount = float(input("请输入您愿意承担的最大风险金额 (USD): "))
    if risk_amount > total_assets:
        print("风险金额不能超过总资产！")
        return
    
    # 计算最大开仓金额
    max_position = risk_amount * leverage
    print(f"您可用的最大开仓金额为: {max_position:.2f} USD")
    
    # 盈亏比计算
    profit_loss_ratio = float(input("请输入盈亏比 (例如 3 表示 3:1): "))
    potential_profit = risk_amount * profit_loss_ratio
    print(f"根据盈亏比，可能盈利金额为: {potential_profit:.2f} USD")
    print(f"根据盈亏比，可能亏损金额为: {risk_amount:.2f} USD")
    
    # 连续亏损计算
    consecutive_losses = int(input("请输入连续亏损次数: "))
    remaining_assets = total_assets
    for i in range(consecutive_losses):
        remaining_assets -= risk_amount
        if remaining_assets <= 0:
            print(f"连续亏损 {i+1} 次后，您的资产已归零。")
            return
    print(f"连续亏损 {consecutive_losses} 次后，您的剩余资产为: {remaining_assets:.2f} USD")
    
    # 复利计算
    periods = int(input("请输入复利计算的周期数量: "))
    rate_of_return = float(input("请输入每周期收益率（例如 0.05 表示 5%）: "))
    
    compounded_assets = total_assets
    for _ in range(periods):
        compounded_assets *= (1 + rate_of_return)
    
    print(f"{periods} 个周期后，您的总资产为: {compounded_assets:.2f} USD")
    
    # 输出最终信息
    print("=== 合约计算完成 ===")
    print(f"总资产: {total_assets} USD")
    print(f"方向: {'看涨 (做多)' if direction == '多' else '看跌 (做空)'}")
    print(f"杠杆倍数: {leverage}")
    print(f"最大风险: {risk_amount} USD")
    print(f"复利计算后总资产: {compounded_assets:.2f} USD")
    print(f"可能亏损金额: {risk_amount:.2f} USD")
    print(f"可能盈利金额: {potential_profit:.2f} USD")

# 运行计算器
calculate_contract_advanced()
