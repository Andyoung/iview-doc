<template>
    <i-article>
        <article>
            <h1>Menu 导航菜单</h1>
            <Anchor title="概述" h2></Anchor>
            <p>为页面和功能提供导航的菜单列表，常用于网站顶部和左侧。</p>
            <blockquote>注意：非 template/render 模式下，需使用 <code>i-menu</code>。</blockquote>
            <Anchor title="代码示例" h2></Anchor>
            <Demo title="顶部导航" vertical hide-code>
                <div slot="demo">
                    <Menu mode="horizontal" :theme="theme1" active-name="1">
                        <Menu-item name="1">
                            <Icon type="ios-paper"></Icon>
                            内容管理
                        </Menu-item>
                        <Menu-item name="2">
                            <Icon type="ios-people"></Icon>
                            用户管理
                        </Menu-item>
                        <Submenu name="3">
                            <template slot="title">
                                <Icon type="stats-bars"></Icon>
                                统计分析
                            </template>
                            <Menu-group title="使用">
                                <Menu-item name="3-1">新增和启动</Menu-item>
                                <Menu-item name="3-2">活跃分析</Menu-item>
                                <Menu-item name="3-3">时段分析</Menu-item>
                            </Menu-group>
                            <Menu-group title="留存">
                                <Menu-item name="3-4">用户留存</Menu-item>
                                <Menu-item name="3-5">流失用户</Menu-item>
                            </Menu-group>
                        </Submenu>
                        <Menu-item name="4">
                            <Icon type="settings"></Icon>
                            综合设置
                        </Menu-item>
                    </Menu>
                    <br>
                    <p>切换主题</p>
                    <Radio-group v-model="theme1">
                        <Radio label="light"></Radio>
                        <Radio label="dark"></Radio>
                        <Radio label="primary"></Radio>
                    </Radio-group>
                </div>
                <div slot="desc">
                    <p>水平的顶部导航菜单。</p>
                    <p>通过设置属性 <code>theme</code> 为 <code>light</code>、<code>dark</code>、<code>primary</code> 可以选择主题。</p>
                    <p>通过事件 <code>on-select</code> 可以得到点击菜单的 name 值，从而控制页面路由或自定义操作。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.base }}</i-code>
            </Demo>
            <Demo title="侧栏导航" vertical hide-code>
                <div slot="demo">
                    <Row>
                        <Col span="8">
                            <Menu :theme="theme2">
                                <Submenu name="1">
                                    <template slot="title">
                                        <Icon type="ios-paper"></Icon>
                                        内容管理
                                    </template>
                                    <Menu-item name="1-1">文章管理</Menu-item>
                                    <Menu-item name="1-2">评论管理</Menu-item>
                                    <Menu-item name="1-3">举报管理</Menu-item>
                                </Submenu>
                                <Submenu name="2">
                                    <template slot="title">
                                        <Icon type="ios-people"></Icon>
                                        用户管理
                                    </template>
                                    <Menu-item name="2-1">新增用户</Menu-item>
                                    <Menu-item name="2-2">活跃用户</Menu-item>
                                </Submenu>
                                <Submenu name="3">
                                    <template slot="title">
                                        <Icon type="stats-bars"></Icon>
                                        统计分析
                                    </template>
                                    <Menu-group title="使用">
                                        <Menu-item name="3-1">新增和启动</Menu-item>
                                        <Menu-item name="3-2">活跃分析</Menu-item>
                                        <Menu-item name="3-3">时段分析</Menu-item>
                                    </Menu-group>
                                    <Menu-group title="留存">
                                        <Menu-item name="3-4">用户留存</Menu-item>
                                        <Menu-item name="3-5">流失用户</Menu-item>
                                    </Menu-group>
                                </Submenu>
                            </Menu>
                        </Col>
                        <Col span="8">
                            <Menu :theme="theme2" active-name="1-2" :open-names="['1']">
                                <Submenu name="1">
                                    <template slot="title">
                                        <Icon type="ios-paper"></Icon>
                                        内容管理
                                    </template>
                                    <Menu-item name="1-1">文章管理</Menu-item>
                                    <Menu-item name="1-2">评论管理</Menu-item>
                                    <Menu-item name="1-3">举报管理</Menu-item>
                                </Submenu>
                                <Submenu name="2">
                                    <template slot="title">
                                        <Icon type="ios-people"></Icon>
                                        用户管理
                                    </template>
                                    <Menu-item name="2-1">新增用户</Menu-item>
                                    <Menu-item name="2-2">活跃用户</Menu-item>
                                </Submenu>
                                <Submenu name="3">
                                    <template slot="title">
                                        <Icon type="stats-bars"></Icon>
                                        统计分析
                                    </template>
                                    <Menu-group title="使用">
                                        <Menu-item name="3-1">新增和启动</Menu-item>
                                        <Menu-item name="3-2">活跃分析</Menu-item>
                                        <Menu-item name="3-3">时段分析</Menu-item>
                                    </Menu-group>
                                    <Menu-group title="留存">
                                        <Menu-item name="3-4">用户留存</Menu-item>
                                        <Menu-item name="3-5">流失用户</Menu-item>
                                    </Menu-group>
                                </Submenu>
                            </Menu>
                        </Col>
                        <Col span="8">
                            <Menu :theme="theme2" :open-names="['1']" accordion>
                                <Submenu name="1">
                                    <template slot="title">
                                        <Icon type="ios-paper"></Icon>
                                        内容管理
                                    </template>
                                    <Menu-item name="1-1">文章管理</Menu-item>
                                    <Menu-item name="1-2">评论管理</Menu-item>
                                    <Menu-item name="1-3">举报管理</Menu-item>
                                </Submenu>
                                <Submenu name="2">
                                    <template slot="title">
                                        <Icon type="ios-people"></Icon>
                                        用户管理
                                    </template>
                                    <Menu-item name="2-1">新增用户</Menu-item>
                                    <Menu-item name="2-2">活跃用户</Menu-item>
                                </Submenu>
                                <Submenu name="3">
                                    <template slot="title">
                                        <Icon type="stats-bars"></Icon>
                                        统计分析
                                    </template>
                                    <Menu-group title="使用">
                                        <Menu-item name="3-1">新增和启动</Menu-item>
                                        <Menu-item name="3-2">活跃分析</Menu-item>
                                        <Menu-item name="3-3">时段分析</Menu-item>
                                    </Menu-group>
                                    <Menu-group title="留存">
                                        <Menu-item name="3-4">用户留存</Menu-item>
                                        <Menu-item name="3-5">流失用户</Menu-item>
                                    </Menu-group>
                                </Submenu>
                            </Menu>
                        </Col>
                    </Row>
                    <br>
                    <p>切换主题</p>
                    <Radio-group v-model="theme2">
                        <Radio label="light"></Radio>
                        <Radio label="dark"></Radio>
                    </Radio-group>
                </div>
                <div slot="desc">
                    <p>垂直导航菜单，可以内嵌子菜单。</p>
                    <p>设置 <code>active-name</code> 可以选中指定的菜单，设置 <code>open-names</code> 可以展开指定的子菜单。</p>
                    <p>设置属性 <code>accordion</code> 可以开启手风琴模式，每次只能展开一个子菜单。</p>
                    <p>通过设置属性 <code>theme</code> 为 <code>light</code>、<code>dark</code> 可以选择主题，侧栏菜单不支持 primary 主题。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.vertical }}</i-code>
            </Demo>
            <Demo title="分组" vertical hide-code>
                <div slot="demo">
                    <Menu :theme="theme3" active-name="1">
                        <Menu-group title="内容管理">
                            <Menu-item name="1">
                                <Icon type="document-text"></Icon>
                                文章管理
                            </Menu-item>
                            <Menu-item name="2">
                                <Icon type="chatbubbles"></Icon>
                                评论管理
                            </Menu-item>
                        </Menu-group>
                        <Menu-group title="统计分析">
                            <Menu-item name="3">
                                <Icon type="heart"></Icon>
                                用户留存
                            </Menu-item>
                            <Menu-item name="4">
                                <Icon type="heart-broken"></Icon>
                                流失用户
                            </Menu-item>
                        </Menu-group>
                    </Menu>
                    <br>
                    <p>切换主题</p>
                    <Radio-group v-model="theme3">
                        <Radio label="light"></Radio>
                        <Radio label="dark"></Radio>
                    </Radio-group>
                </div>
                <div slot="desc">
                    <p>使用 <code>Menu-group</code> 组件进行分组，注意：</p>
                    <ul>
                        <li> <code>Menu-group</code> 只能用在 <code>Menu</code> 和 <code>Submenu</code> 内。</li>
                        <li> <code>Submenu</code> 只能用在 <code>Menu</code> 内，不能用在 <code>Menu-group</code> 和 <code>Menu-item</code> 内。</li>
                    </ul>
                </div>
                <i-code lang="html" slot="code">{{ code.group }}</i-code>
            </Demo>
            <div class="api">
                <Anchor title="API" h2></Anchor>
                <Anchor title="Menu props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>mode</td>
                            <td>菜单类型，可选值为 <code>horizontal</code>（水平） 和 <code>vertical</code>（垂直）</td>
                            <td>String</td>
                            <td>vertical</td>
                        </tr>
                        <tr>
                            <td>theme</td>
                            <td>主题，可选值为 <code>light</code>、<code>dark</code>、<code>primary</code>，其中 primary 只适用于 <code>mode="horizontal"</code></td>
                            <td>String</td>
                            <td>light</td>
                        </tr>
                        <tr>
                            <td>active-name</td>
                            <td>激活菜单的 name 值</td>
                            <td>String | Number</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td>open-names</td>
                            <td>展开的 Submenu 的 name 集合</td>
                            <td>Array</td>
                            <td>[]</td>
                        </tr>
                        <tr>
                            <td>accordion</td>
                            <td>是否开启手风琴模式，开启后每次至多展开一个子菜单</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>width</td>
                            <td>导航菜单的宽度，只在 <code>mode="vertical"</code> 时有效，如果使用 <code>Col</code> 等布局，建议设置为 <code>auto</code></td>
                            <td>String</td>
                            <td>240px</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Menu events" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>事件名</th>
                            <th>说明</th>
                            <th>返回值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>on-select</td>
                            <td>选择菜单（Menu-item）时触发</td>
                            <td>name</td>
                        </tr>
                        <tr>
                            <td>on-open-change</td>
                            <td>当 展开/收起 子菜单时触发</td>
                            <td>当前展开的 Submenu 的 name 值数组</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Menu methods" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>方法名</th>
                            <th>说明</th>
                            <th>参数</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>updateOpened</td>
                            <td>手动更新展开的子目录，注意要在 $nextTick 里调用</td>
                            <td>无</td>
                        </tr>
                        <tr>
                            <td>updateActiveName</td>
                            <td>手动更新当前选择项，注意要在 $nextTick 里调用</td>
                            <td>无</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="MenuItem props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>name</td>
                            <td>菜单项的唯一标识，必填</td>
                            <td>String | Number</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Submenu props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>name</td>
                            <td>子菜单的唯一标识，必填</td>
                            <td>String | Number</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Submenu slot" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>名称</th>
                            <th>说明</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>无</td>
                            <td>菜单项</td>
                        </tr>
                        <tr>
                            <td>title</td>
                            <td>子菜单标题</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="MenuGroup props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>title</td>
                            <td>分组标题</td>
                            <td>String</td>
                            <td>空</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </article>
    </i-article>
</template>
<script>
    import iArticle from '../../components/article.vue';
    import iCode from 'iCode';
    import Demo from '../../components/demo.vue';
    import Code from '../../code/menu';
    import Anchor from '../../components/anchor.vue';

    export default {
        components: {
            iArticle,
            iCode,
            Demo,
            Anchor
        },
        data () {
            return {
                code: Code,
                theme1: 'light',
                theme2: 'light',
                theme3: 'light'
            }
        },
        methods: {

        }
    }
</script>