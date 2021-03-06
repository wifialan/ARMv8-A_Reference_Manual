# Arm架构参考手册

Armv8,Arm应用程序配置文件架构

版权所有 © 2013-2021 Arm Limited 或其附属公司。版权所有。

发布信息

本文档的发布版本如下: 

<p align="right">发布历史</p>

| 日期           | 期号  | 机密性                       | 变更                                            |
| :------------- | :---- | ---------------------------- | ----------------------------------------------- |
| **2013.04.30** | A.a-1 | 保密公测草稿资料             | 第一版公测草稿版本，有限发行                    |
| **2013.06.12** | A.a-2 | 保密-公测草稿资料            | 第二版公测草稿版本，有限发行                    |
| **2013.09.04** | A.a   | 非密-公测版本                | 公测版本发布                                    |
| **2013.12.24** | A.b   | 非密-公测版本                | 第二版公测版本发布                              |
| **2014.07.18** | A.c   | 非密-公测版本                | 第三版公测版本发布                              |
| **2014.10.09** | A.d   | 非密-公测版本                | 第四版公测版本发布                              |
| **2014.12.17** | A.e   | 非密-公测版本                | 第五版公测版本发布                              |
| **2015.02.25** | A.f   | 非密-公测版本                | 第六版公测版本发布                              |
| **2015.07.10** | A.g   | 非密-公测版本                | 第七版公测版本发布                              |
| **2015.09.30** | A.h   | 非密-公测版本                | 第八版公测版本发布                              |
| **2016.01.28** | A.i   | 非密-公测版本                | 第九版公测版本发布                              |
| **2016.06.03** | A.j   | 非密-EAC版本                 | EAC版本发布                                     |
| **2017.09.26** | A.k   | 非密-Armv8.0 EAC             | 更新EAC版本发布                                 |
| **2019.12.20** | B.a   | 非密- Armv8.1  EAC，v8.2公测 | 包含Armv8.1和Armv8.2的最初版本                  |
| **2018.09.26** | B.b   | 非密-Armv8.2 EAC             | 初始Armv8.2 EAC版本，合并了SPE                  |
| **2017.12.20** | C.a   | 非密-Armv8.3  EAC            | 初始Armv8.3 EAC版本发布                         |
| **2018.10.31** | D.a   | 非密-Armv8.4 EAC             | 初始Armv8.4 EAC版本发布                         |
| **2019.04.29** | D.b   | 非密-Armv8.4  EAC            | 更新Armv8.4 EAC版本，包含可访问性的变化         |
| **2019.07.05** | E.a   | 非密-Armv8.5 EAC             | 初始Armv8.5 EAC版本发布                         |
| **2020.02.20** | F.a   | 非密-Armv8.6 公测版本        | 初始Armv8.6 公测版本发布                        |
| **2020.03.31** | F.b   | 非密- Armv8.5  EAC，v8.6公测 | Armv8.5 EAC版本发布，  初始Armv8.6 公测版本发布 |
| **2020.07.17** | F.c   | 非密- Armv8.6 EAC            | 初始Armv8.6 EAC版本发布                         |
| **2021.01.22** | G.a   | 非密- Armv8.7  EAC           | 初始Armv8.7 EAC版本发布                         |
| **2021.07.22** | G.b   | 非密- Armv8.7 EAC            | 更新Armv8.7 EAC版本发布                         |

**特别声明**

本文档受版权和其他相关权利以及所含信息的实践或实施的保护本文档中的内容可能受到一项或多项专利或未决专利申请的保护。本文档的任何部分都不得未经 Arm 事先明确书面许可，以任何方式以任何形式复制。没有许可，明示或暗示，由除非特别说明，否则本文档授予禁止反言或其他任何知识产权。

您对本文档中信息的访问取决于您接受您不会使用或允许他人使用,用于确定实施是否侵犯任何第三方专利的信息。

本文档按“原样”提供。 ARM 不提供任何陈述和保证，明示的、默示的或法定的，包括但不限于以下的默示保证适销性、令人满意的质量、非侵权或特定的适用性与文件有关的目的。 为免生疑问，Arm 对以下方面不作任何陈述：并且未进行任何分析以识别或理解专利、版权、商业秘密或其他权利的范围和内容。

本文档可能包含技术错误或印刷错误。

在法律未禁止的范围内，ARM 在任何情况下均不对任何损害负责，包括但不限于任何直接的、间接的、特殊的、附带的、惩罚性的或后果性损害，无论是由何种原因引起的，也不论责任理论如何，出于对本文档的任何使用，即使 ARM 已被告知此类可能性损害赔偿。

本文档仅包含商业项目。 您应负责确保任何使用、复制或披露本文件完全符合任何相关的出口法律和法规，以确保本文件或其任何部分不违反此类出口法律直接或间接出口。 在提及 Arm 的客户时使用“合作伙伴”一词无意创建或提及与任何其他公司的任何合伙关系。 Arm 可能会对本文档进行更改随时，恕不另行通知。

 为方便起见，本文档可能被翻译成其他语言，您同意如果与本文件的英文版及任何译文，以英文版协议的条款为准。

 Arm 公司徽标和标有 ® 或 ™ 的文字是 Arm Limited（或其关联公司）的注册商标或商标在美国和/或其他地方。 版权所有。 本文档中提及的其他品牌和名称可能是他们各自的所有者。 您必须遵守 Arm 的商标使用指南：

http://www.arm.com/company/policies/trademarks.

版权所有 © 2013-2021 Arm Limited（或其附属公司）。 版权所有。

Arm有限公司。 公司 02557590 在英国注册。

110 Fulbourn 路，剑桥，英格兰 CB1 9NJ。

 （LES-PRE-20349 版本 21.0）

在本文档中，术语 Arm 用于指代公司时，表示“Arm 或其任何适当的关联公司”

