import React, { useState } from 'react';
import { Play, TrendingUp, Shield, BarChart3, Zap, CheckCircle, ArrowRight, Menu, X, Mail, Globe } from 'lucide-react';

export default function KanarieLP() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    setIsMenuOpen(false);
  };

  return (
    <div className="min-h-screen bg-white text-slate-800 font-sans selection:bg-blue-100">
      {/* Navigation */}
      <nav className="fixed w-full bg-white/90 backdrop-blur-md z-50 border-b border-slate-200 shadow-sm">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-20">
            <div className="flex items-center">
              <span className="text-2xl font-bold text-blue-900 tracking-tighter">Kanarie AI</span>
            </div>
            
            {/* Desktop Menu */}
            <div className="hidden md:flex space-x-8 items-center">
              <button onClick={() => scrollToSection('problems')} className="text-slate-600 hover:text-blue-600 font-medium transition">課題</button>
              <button onClick={() => scrollToSection('solution')} className="text-slate-600 hover:text-blue-600 font-medium transition">解決策</button>
              <button onClick={() => scrollToSection('comparison')} className="text-slate-600 hover:text-blue-600 font-medium transition">他社比較</button>
              <button 
                onClick={() => scrollToSection('contact')}
                className="bg-blue-600 text-white px-6 py-2.5 rounded-full font-bold hover:bg-blue-700 transition shadow-lg hover:shadow-blue-500/30"
              >
                お問い合わせ
              </button>
            </div>

            {/* Mobile Menu Button */}
            <div className="md:hidden">
              <button onClick={() => setIsMenuOpen(!isMenuOpen)} className="text-slate-600">
                {isMenuOpen ? <X size={28} /> : <Menu size={28} />}
              </button>
            </div>
          </div>
        </div>

        {/* Mobile Menu */}
        {isMenuOpen && (
          <div className="md:hidden bg-white border-t border-slate-100">
            <div className="px-4 pt-2 pb-6 space-y-2 shadow-xl">
              <button onClick={() => scrollToSection('problems')} className="block w-full text-left py-3 text-slate-600 font-medium">課題</button>
              <button onClick={() => scrollToSection('solution')} className="block w-full text-left py-3 text-slate-600 font-medium">解決策</button>
              <button onClick={() => scrollToSection('comparison')} className="block w-full text-left py-3 text-slate-600 font-medium">他社比較</button>
              <button onClick={() => scrollToSection('contact')} className="block w-full text-center py-3 mt-4 bg-blue-600 text-white rounded-lg font-bold">お問い合わせ</button>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section className="pt-32 pb-20 lg:pt-48 lg:pb-32 relative overflow-hidden bg-gradient-to-b from-blue-50 to-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div className="text-center max-w-4xl mx-auto">
            <div className="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-blue-100 text-blue-700 font-semibold text-sm mb-8">
              <span className="flex h-2 w-2 rounded-full bg-blue-600 animate-pulse"></span>
              次世代の広告戦略
            </div>
            <h1 className="text-4xl md:text-6xl lg:text-7xl font-extrabold text-slate-900 tracking-tight leading-tight mb-8">
              「ただの広告」から<br className="hidden md:block" />
              <span className="text-blue-600">「資産」</span>へ。
            </h1>
            <p className="text-xl text-slate-600 mb-10 max-w-2xl mx-auto leading-relaxed">
              Meta・TikTok・Google検索広告の限界を超える。<br />
              Kanarie AIは、YouTubeショートを活用した<span className="font-bold text-slate-800">「ストック型マーケティング」</span>を実現します。
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center">
              <button onClick={() => scrollToSection('contact')} className="bg-blue-600 text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-700 transition shadow-xl hover:shadow-blue-500/30 flex items-center justify-center gap-2">
                デモを依頼する <ArrowRight size={20} />
              </button>
              <button onClick={() => scrollToSection('solution')} className="bg-white text-slate-700 border border-slate-200 px-8 py-4 rounded-full font-bold text-lg hover:bg-slate-50 transition flex items-center justify-center">
                詳細を見る
              </button>
            </div>
          </div>
        </div>
        
        {/* Abstract Background Elements */}
        <div className="absolute top-0 left-0 w-full h-full overflow-hidden -z-10 opacity-30">
          <div className="absolute top-1/4 left-10 w-72 h-72 bg-blue-200 rounded-full mix-blend-multiply filter blur-3xl animate-blob"></div>
          <div className="absolute top-1/4 right-10 w-72 h-72 bg-cyan-200 rounded-full mix-blend-multiply filter blur-3xl animate-blob animation-delay-2000"></div>
          <div className="absolute -bottom-8 left-1/2 w-72 h-72 bg-indigo-200 rounded-full mix-blend-multiply filter blur-3xl animate-blob animation-delay-4000"></div>
        </div>
      </section>

      {/* Problem Section */}
      <section id="problems" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl md:text-4xl font-bold text-slate-900 mb-4">従来の広告モデルの「限界」</h2>
            <p className="text-slate-500">フロー型広告に依存するリスクを感じていませんか？</p>
          </div>
          
          <div className="grid md:grid-cols-3 gap-8">
            {[
              {
                icon: <Zap size={40} className="text-red-500" />,
                title: "広告停止 ＝ 収益ゼロ",
                desc: "MetaやGoogle検索広告は、予算を止めた瞬間に流入が完全に停止します。資産として残りません。"
              },
              {
                icon: <TrendingUp size={40} className="text-red-500" />,
                title: "CPAの高騰",
                desc: "競合の激化により、獲得単価は年々上昇傾向。同じ予算での獲得効率は下がる一方です。"
              },
              {
                icon: <BarChart3 size={40} className="text-red-500" />,
                title: "資産にならない",
                desc: "どれだけ費用をかけても、自社メディアのパワー（チャンネル登録者等）は蓄積されにくい構造です。"
              }
            ].map((item, index) => (
              <div key={index} className="bg-slate-50 p-8 rounded-2xl border border-slate-100 hover:shadow-lg transition duration-300">
                <div className="bg-white w-16 h-16 rounded-xl flex items-center justify-center shadow-sm mb-6">
                  {item.icon}
                </div>
                <h3 className="text-xl font-bold text-slate-900 mb-3">{item.title}</h3>
                <p className="text-slate-600 leading-relaxed">{item.desc}</p>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Solution Section */}
      <section id="solution" className="py-20 bg-slate-900 text-white relative overflow-hidden">
        <div className="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1451187580459-43490279c0fa?q=80&w=2072&auto=format&fit=crop')] bg-cover bg-center opacity-10"></div>
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div className="grid lg:grid-cols-2 gap-16 items-center">
            <div>
              <div className="inline-block px-4 py-1 bg-blue-500/20 text-blue-300 rounded-full text-sm font-semibold mb-6 border border-blue-500/30">
                Kanarie AIのソリューション
              </div>
              <h2 className="text-3xl md:text-5xl font-bold mb-6 leading-tight">
                「広告媒体としての強さ」<br/>×<br/><span className="text-blue-400">「チャンネル資産化」</span>
              </h2>
              <p className="text-slate-300 text-lg mb-8 leading-relaxed">
                KanarieのAIショート広告は、単なるLPへの誘導装置ではありません。動画自体がチャンネルに残り、継続的な再生を生み出す「ストック型マーケティング」を実現します。
              </p>
              
              <ul className="space-y-4">
                {[
                  "広告配信終了後もオーガニック再生が続く",
                  "質の高い視聴者が「チャンネル登録者」として蓄積",
                  "将来的な集客コスト(CPA)を劇的に引き下げる"
                ].map((item, i) => (
                  <li key={i} className="flex items-center gap-3">
                    <CheckCircle className="text-blue-400 flex-shrink-0" size={24} />
                    <span className="text-lg font-medium">{item}</span>
                  </li>
                ))}
              </ul>
            </div>
            
            <div className="relative">
              <div className="absolute inset-0 bg-blue-500 blur-3xl opacity-20 rounded-full"></div>
              <div className="bg-slate-800/50 backdrop-blur-xl border border-slate-700 rounded-3xl p-8 relative">
                <div className="flex items-center gap-4 mb-8">
                  <div className="w-12 h-12 bg-red-600 rounded-lg flex items-center justify-center">
                    <Play className="text-white fill-current" size={24} />
                  </div>
                  <div>
                    <div className="text-sm text-slate-400">Target Platform</div>
                    <div className="text-xl font-bold">YouTube Shorts</div>
                  </div>
                </div>
                
                <div className="space-y-6">
                  <div className="bg-slate-700/50 p-4 rounded-xl">
                    <div className="text-blue-400 font-bold text-sm mb-1">Google AI ターゲティング</div>
                    <div className="text-sm text-slate-300">検索・視聴履歴に基づいた、購買意欲の高いユーザー層へのリーチ</div>
                  </div>
                  <div className="bg-slate-700/50 p-4 rounded-xl">
                    <div className="text-blue-400 font-bold text-sm mb-1">圧倒的低コスト</div>
                    <div className="text-sm text-slate-300">1再生 0.2円〜5円。Meta等と比較して安価なCPM</div>
                  </div>
                  <div className="bg-slate-700/50 p-4 rounded-xl">
                    <div className="text-blue-400 font-bold text-sm mb-1">高い拡散力（バイラリティ）</div>
                    <div className="text-sm text-slate-300">AIレコメンド最適化で、長期間かつ広範囲へ拡散</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Comparison Section */}
      <section id="comparison" className="py-20 bg-slate-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl md:text-4xl font-bold text-slate-900 mb-4">他媒体との徹底比較</h2>
            <p className="text-slate-500">なぜ今、Kanarie AIが選ばれるのか</p>
          </div>

          <div className="overflow-x-auto">
            <div className="inline-block min-w-full align-middle">
              <div className="border border-slate-200 rounded-2xl overflow-hidden shadow-sm bg-white">
                <table className="min-w-full divide-y divide-slate-200">
                  <thead className="bg-slate-50">
                    <tr>
                      <th scope="col" className="px-6 py-4 text-left text-sm font-semibold text-slate-500 uppercase tracking-wider">媒体</th>
                      <th scope="col" className="px-6 py-4 text-left text-sm font-semibold text-slate-500 uppercase tracking-wider">資産性(ストック)</th>
                      <th scope="col" className="px-6 py-4 text-left text-sm font-semibold text-slate-500 uppercase tracking-wider">ターゲティング精度</th>
                      <th scope="col" className="px-6 py-4 text-left text-sm font-semibold text-slate-500 uppercase tracking-wider">持続的効果</th>
                      <th scope="col" className="px-6 py-4 text-left text-sm font-semibold text-slate-500 uppercase tracking-wider">コスト感</th>
                    </tr>
                  </thead>
                  <tbody className="bg-white divide-y divide-slate-200">
                    <tr className="bg-blue-50/50">
                      <td className="px-6 py-5 whitespace-nowrap">
                        <div className="flex items-center">
                          <span className="font-bold text-blue-700 text-lg">YouTubeショート (Kanarie)</span>
                        </div>
                      </td>
                      <td className="px-6 py-5 whitespace-nowrap">
                        <span className="inline-flex items-center px-3 py-1 rounded-full text-xs font-bold bg-blue-100 text-blue-800">
                          ◎ 極めて高い
                        </span>
                      </td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-700">Google AI活用 (広範囲)</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-700 font-bold">◎ 半永久的</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-700">
                         <span className="font-bold text-green-600">0.2円〜</span> / 再生
                      </td>
                    </tr>
                    <tr>
                      <td className="px-6 py-5 whitespace-nowrap font-medium text-slate-900">Meta (FB/Insta)</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× なし (フロー型)</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">興味関心・属性</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× 停止でゼロ</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">中〜高</td>
                    </tr>
                    <tr>
                      <td className="px-6 py-5 whitespace-nowrap font-medium text-slate-900">TikTok広告</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× なし (フロー型)</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">若年層中心</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× 停止でゼロ</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">中</td>
                    </tr>
                     <tr>
                      <td className="px-6 py-5 whitespace-nowrap font-medium text-slate-900">Googleリスティング</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× なし</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">キーワード (顕在層)</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">× 停止でゼロ</td>
                      <td className="px-6 py-5 whitespace-nowrap text-sm text-slate-500">高 (50円〜/click)</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Tech / Features Section */}
      <section className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid md:grid-cols-2 gap-12 items-center">
            <div className="order-2 md:order-1">
              <div className="bg-slate-100 rounded-3xl p-8 space-y-6">
                 {/* Mock UI for AI Analysis */}
                 <div className="bg-white rounded-xl p-4 shadow-sm border border-slate-200">
                    <div className="flex items-center justify-between mb-4">
                        <div className="flex items-center gap-2">
                             <div className="w-2 h-2 rounded-full bg-green-500"></div>
                             <span className="text-xs font-bold text-slate-600">AI OPTIMIZATION ACTIVE</span>
                        </div>
                        <span className="text-xs text-slate-400">Live</span>
                    </div>
                    <div className="space-y-3">
                        <div className="h-2 bg-slate-100 rounded-full overflow-hidden">
                            <div className="h-full w-[85%] bg-blue-500 rounded-full"></div>
                        </div>
                        <div className="flex justify-between text-xs text-slate-500">
                            <span>Creative Pattern A</span>
                            <span className="font-bold text-slate-700">85% Retention</span>
                        </div>
                         <div className="h-2 bg-slate-100 rounded-full overflow-hidden">
                            <div className="h-full w-[45%] bg-slate-300 rounded-full"></div>
                        </div>
                         <div className="flex justify-between text-xs text-slate-500">
                            <span>Creative Pattern B (Stopped)</span>
                            <span className="font-bold text-slate-700">45% Retention</span>
                        </div>
                    </div>
                 </div>
                 
                 <div className="bg-white rounded-xl p-4 shadow-sm border border-slate-200">
                    <div className="flex justify-between items-end">
                        <div>
                            <div className="text-xs text-slate-500 mb-1">Total Subscribers</div>
                            <div className="text-2xl font-bold text-slate-800">+12,450</div>
                        </div>
                         <div className="text-green-500 text-sm font-bold flex items-center">
                            <TrendingUp size={16} className="mr-1" /> +124%
                        </div>
                    </div>
                 </div>
              </div>
            </div>
            
            <div className="order-1 md:order-2">
               <h2 className="text-3xl md:text-4xl font-bold text-slate-900 mb-6">
                 成果を最大化する<br/><span className="text-blue-600">Kanarie AI エンジン</span>
               </h2>
               <div className="space-y-8">
                 <div className="flex gap-4">
                   <div className="flex-shrink-0 w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center text-blue-600 font-bold text-xl">1</div>
                   <div>
                     <h3 className="text-xl font-bold text-slate-900 mb-2">分析 & 生成</h3>
                     <p className="text-slate-600">過去の膨大なヒット動画データをAIが学習。視聴維持率を最大化する構成とスクリプトを自動生成します。</p>
                   </div>
                 </div>
                 <div className="flex gap-4">
                   <div className="flex-shrink-0 w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center text-blue-600 font-bold text-xl">2</div>
                   <div>
                     <h3 className="text-xl font-bold text-slate-900 mb-2">高速ABテスト</h3>
                     <p className="text-slate-600">大量のバリエーションを同時に出稿。人間の手では不可能な速度で「勝ちクリエイティブ」を特定します。</p>
                   </div>
                 </div>
                 <div className="flex gap-4">
                   <div className="flex-shrink-0 w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center text-blue-600 font-bold text-xl">3</div>
                   <div>
                     <h3 className="text-xl font-bold text-slate-900 mb-2">自動最適化</h3>
                     <p className="text-slate-600">成果の出ない動画を停止し、予算を成果の良い動画へ自動配分。CPAを最小化し続けます。</p>
                   </div>
                 </div>
               </div>
            </div>
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section id="contact" className="py-20 bg-blue-900 text-white">
        <div className="max-w-4xl mx-auto px-4 text-center">
          <h2 className="text-3xl md:text-5xl font-bold mb-6">資産を築く広告運用を<br/>始めませんか？</h2>
          <p className="text-blue-200 text-lg mb-10">
            まずはお気軽にお問い合わせください。<br/>
            貴社の課題に合わせたシミュレーションをご提案します。
          </p>
          
          <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 md:p-12 border border-blue-500/30">
            <div className="flex flex-col md:flex-row justify-center gap-6 items-center mb-8">
                <div className="flex items-center gap-3">
                    <Mail className="text-blue-300" />
                    <span className="text-lg">masahiro@capital-design-holdings.com</span>
                </div>
                <div className="hidden md:block w-px h-6 bg-blue-500/50"></div>
                <div className="flex items-center gap-3">
                    <Globe className="text-blue-300" />
                    <span className="text-lg">www.capital-design-holdings.com</span>
                </div>
            </div>
            
            <a 
              href="mailto:masahiro@capital-design-holdings.com?subject=Kanarie AIについてのお問い合わせ"
              className="inline-block w-full md:w-auto bg-white text-blue-900 px-10 py-4 rounded-full font-bold text-xl hover:bg-blue-50 transition shadow-lg transform hover:-translate-y-1"
            >
              お問い合わせ・デモのご依頼
            </a>
            <p className="mt-6 text-sm text-blue-300">
              CAPITAL DESIGN Holdings
            </p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900 text-slate-500 py-8 border-t border-slate-800">
        <div className="max-w-7xl mx-auto px-4 text-center text-sm">
          &copy; {new Date().getFullYear()} Kanarie AI / CAPITAL DESIGN. All rights reserved.
        </div>
      </footer>
    </div>
  );
}
