# matplotlib 使用记录

## 生成散点图,将各个数据点的坐标保存,并通过cv2可视化（样例）
```
    import matplotlib.pyplot as plt
    import cv2
    import numpy as np

    # 示例数据
    data_pos = np.array([[100, 150], [200, 250], [300, 100]])

    # 创建图像和坐标轴
    fig, ax = plt.subplots(figsize=(5, 5), dpi=100)
    plt.ticklabel_format(style='plain')
    # 绘制散点图
    ax.scatter(data_pos[:, 0], data_pos[:, 1], color='red', label='label')

    plt.xlabel('xx')
    plt.ylabel('yy')
    # 设置坐标轴范围
    plt.xlim(0, 400)
    plt.ylim(0, 300)
    plt.title('title')
    leg = plt.legend()
    plt.grid(True)
    # 手动绘制图例，确保图例被创建
    plt.draw()

    # 转换数据坐标为像素坐标
    abs_pos = ax.transData.transform(data_pos)

    # 显示转换后的像素坐标
    print(abs_pos)

    # 保存图像
    plt.savefig('scatter_plot.png', dpi=100)
    # plt.show()

    # 读取图像并在cv2中显示点
    image = cv2.imread('scatter_plot.png')

    # 绘制点
    for x, y in abs_pos:
        y = image.shape[0] - y
        cv2.circle(image, tuple([int(x), int(y)]), 1, (255, 255, 255), -1)

    # 显示图像
    cv2.imshow('Image with Points', image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
注意：在 plt.savefig 中如果设置 bbox_inches='tight'，会导致保存的数据坐标和图片中的点位置存在偏移。
