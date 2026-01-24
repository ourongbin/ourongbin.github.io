---
title: 'Home'
date: 2023-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: hero
    content:
      title: 财多多
      text: 你的智能投资组合管家
      # Hero image (optional)
      image:
        filename: ""
      primary_action:
        url: "/download.html"
        text: "下载财多多，祝您财源滚滚～"
        icon: "arrow-down-tray"
      secondary_action:
        url: "/docs"
        text: "查看文档"
    design:
      # Hero background color (CSS class)
      css_class: "bg-gradient-to-br from-primary-900 to-slate-900 dark:from-primary-900 dark:to-slate-900 text-white"
      background:
        image:
          filename: ""
          filters:
            brightness: 0.5

  - block: features
    content:
      title: 核心功能
      text: 专为个人投资者打造的专业级管理工具
      items:
        - name: 多组合管理
          description: 支持创建无限个投资组合，独立追踪每个组合的持仓和收益。
          icon: chart-pie
        - name: 网格交易
          description: 内置网格交易条件单系统，自动监控价格波动，捕捉震荡收益。
          icon: chart-bar
        - name: Git 自动同步
          description: 数据存储在 Excel 文件中，通过 Git 自动同步到云端，安全可靠。
          icon: code-bracket
        - name: 收益曲线
          description: 自动生成交互式收益曲线图表，直观展示资产增长趋势。
          icon: presentation-chart-line
    design:
      columns: "3"
      css_class: "bg-gray-50 dark:bg-gray-900"

  - block: cta-card
    content:
      title: 准备好开始了吗？
      text: 立即下载 财多多，开启你的财富增值之旅。
      button:
        text: 前往 GitHub 下载
        url: https://github.com/ourongbin/financial-manager
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700 text-white"
---
