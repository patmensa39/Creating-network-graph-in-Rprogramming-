# Creating-network-graph-in-Rprogramming-
install.packages("sna")
install.packages("igraph")
pacman::p_load(pacman, sna, igraph)
### reading the data 
data <- read.table("undirected.txt") 
view(data)
head(data)

graph1 <- graph_from_data_frame(data, directed = FALSE, vertices = NULL)
plot(graph1)

### creating sample graphs
philant_full <- make_full_graph(10, directed = FALSE)
plot(philant_full)

### creating ring graph
philant_ring <- make_ring(15, directed = FALSE, mutual = FALSE, circular = TRUE )
plot(philant_ring)

### creating a star graph 
philant_star <- make_star(30, center = 1)
plot(philant_star)

### creating random graphs 
philant_gnp <- sample_gnp(20, 0.3, directed = FALSE, loops = FALSE)
plot(philant_gnp)

philant_gnm <- sample_gnm(20, 50, directed = FALSE, loops = FALSE)
plot(philant_gnm)

philant_gnm <- sample_gnm(20, 25, directed = FALSE, loops = FALSE)
plot(philant_gnm)

### preferential attachment 
philant_gpa <- sample_pa(20, power = 1)
plot(philant_gpa)
