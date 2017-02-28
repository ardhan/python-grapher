import sys
print "Program ini akan mencari shortest path"

#menentukan jumlah titik
cNode = eval(raw_input("Ada berapa kota yang ingin dilewati: "))

#menentukan nama kota
nodeName = []
for i in range(0,cNode):
    nodeName.append(raw_input("Kota "+str(i+1)+": "))

#menentukan keterhubungan
print "Tentukan jarak antar kota"

conn = []
for i in range(0,len(nodeName)):
    for j in range(i,len(nodeName)):
        if (j != i):
            text = "Jarak "+nodeName[i]+" "+nodeName[j]+" = "
            jarak = eval(raw_input(text))
            conn.append((i,j,jarak))
            conn.append((j,i,jarak))

#finding length
def length(node_i,node_j):
    for edge in conn:
        if( (edge[0] == node_i) & (edge[1] == node_j) ):
            return edge[2]

print
for i in range(0,len(nodeName)):
    print "[",i,"]",nodeName[i]


start = eval(raw_input("Pilih titik awal (angka)"))

print "Mencari jarak minimum dari",nodeName[start]



#memproses
dist = []
NodePrev = []
Q = [] #Q adalah titik yang belum dikunjungi

for i in range(0,len(nodeName)):
    dist.append(99999)
    NodePrev.append(-1)
    Q.append(i)

dist[start] = 0

itr = 1
while(len(Q) > 0):
    #u <<< vertex in Q with min dist[u]    // Node with the least distance will be selected first
    print itr
    print "Q = ", Q
    minDist = min(dist)
    u = dist.index(minDist)

    print "Minimum distance = "+str(minDist)
    print "Minimum distance at Q["+str(u)+"]"

    #remove u from Q
    print "Q["+str(u)+"] from Q"
    del Q[u]
    print "Q now is", Q

    # for each neighbor v of u:           // where v is still in Q.
    alt = 0
    for v in Q:
        #alt <<< dist[u] + length(u, v)
        print length(u,v)
        alt = dist[u] + length(u,v)
        #if alt < dist[v]:               // A shorter path to v has been found
        if(alt < dist[v]):
            dist[v] = alt
            NodePrev[v] = u

    itr += 1

print NodePrev
print dist[v]
