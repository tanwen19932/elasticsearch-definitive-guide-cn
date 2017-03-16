## 可扩展性规划

在某些公司Elasticsearch被用来每天索引和检索PB级别的数据，但大多情况我们是从一个相对小很多的数据集开始系统建设的。虽然我们希望能成为下一个Facebook，但是现实往往比理想更骨感。虽然我们从当下开始建设，但之后横向扩展的灵活性和简便性还是必须考虑的。

ELasticsearch天生就是可扩展的。无论是运行在你的个人电脑之上还是运行在由数百个节点构成的集群之上，ELasticsearch都能很好的工作而且两者之间的使用体验并不会有太大的差异。从一个小集群扩展到一个大集群的过程几乎是自动化的、自然而然的。从一个大集群扩展到一个巨型集群会需要一点规划与设计，但是相对来说还是比较自然的。

当然，Elasticsearch也不是包治百病的灵丹妙药，它也有自身的限制。如果你了解这些限制并且能很好的规避它们，这个扩展的过程将会比较平顺。否则你不善待Elasticsearch，它也不会让你很好过。

Elasticsearch的默认设置足以支撑你的系统走很长的路，但是为了更好的利用资源，你还是要认真的设计系统中的数据流。我们将会讨论两个通用的数据流场景：基于时间的数据流（比如日志事件、社交网络时间轴这些基于时间相关性的数据）和基于用户的数据流（比如大规模的数据集合可以按照用户/客户进行切分的场景）。

本章我们将帮助你在系统建设早期做出正确的决策，从而尽可能避免日后意想不到的麻烦。