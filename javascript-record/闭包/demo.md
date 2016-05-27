<h1>闭包 DEMO</h1>
<h3>结果缓存</h3>
<p>那么我们就需要将计算出来的值存储起来，当调用这个函数的时候，首先在缓存中查找，如果找不到，则进行计算，然后更新缓存并返回值，如果找到了，直接返回查找到的值即可。<b>闭包正是可以做到这一点，因为它不会释放外部的引用</b>，从而函数内部的值可以得以保留。</p>
<pre>
var CachedSearchBox = (function() {
  var cache = {},
    count = [];
  return {
    attachSearchBox: function(dsid) {
      if (dsid in cache) { //如果结果在缓存中    
        return cache[dsid]; //直接返回缓存中的对象    
      }
      var fsb = new uikit.webctrl.SearchBox(dsid); //新建    
      cache[dsid] = fsb; //更新缓存    
      if (count.length > 100) { //保正缓存的大小<=100    
        delete cache[count.shift()];
      }
      return fsb;
    },

    clearSearchBox: function(dsid) {
      if (dsid in cache) {
        cache[dsid].clearSelection();
      }
    }
  };
})();
</pre>
